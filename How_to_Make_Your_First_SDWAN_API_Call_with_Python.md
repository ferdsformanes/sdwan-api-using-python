# How to Make Your First SD‑WAN API Call with Python (Login + Get Devices)

This guide shows the shortest practical way to:

1. **Log in** to Cisco Catalyst SD‑WAN Manager (vManage) using Python
2. **Call** a real REST API endpoint to **get the device list**
3. **Print** device names and IDs

---

## Step 1 — Install the required library

```bash
pip install requests
```

---

## Step 2 — Create the script

Create a file named:

```text
get_sdwan_devices.py
```

Paste the code below.

---

## Step 3 — Python code (Login + Get Devices)

```python
# Cisco Catalyst SD-WAN Manager API: Get Device List with Python Requests

import requests
import urllib3

# Ignore SSL warnings for the sandbox (self-signed certs)
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

# Sandbox credentials
HOST = "https://sandbox-sdwan-2.cisco.com"
USERNAME = "devnetuser"
PASSWORD = "RG!_Yw919_83"

# Create a requests session
session = requests.Session()

# Step 1: Login and get JSESSIONID
login_url = f"{HOST}/j_security_check"
payload = {"j_username": USERNAME, "j_password": PASSWORD}
resp = session.post(login_url, data=payload, verify=False)

if resp.status_code != 200 or "JSESSIONID" not in session.cookies:
    raise Exception("Login failed!")

print("JSESSIONID:", session.cookies.get("JSESSIONID"))
print("Logged in successfully")

# Step 2: Retrieve device list
devices_url = f"{HOST}/dataservice/device"
resp = session.get(devices_url, verify=False)

if resp.status_code != 200:
    raise Exception(f"Failed to retrieve devices: {resp.status_code}")

devices = resp.json()

print("
Retrieved devices:")
for d in devices["data"]:
    print(f"- {d['host-name']} ({d['deviceId']})")
```

---

## Step 4 — Run the script

```bash
python get_sdwan_devices.py
```

---

## What’s happening (quick)

- **Login**: `POST /j_security_check` returns a session cookie (**JSESSIONID**) that `requests.Session()` keeps for you.
- **Get devices**: `GET /dataservice/device` returns device inventory in **JSON**.

---

## Next ideas (Episode 2+)

- Get **alarms** via API and filter critical ones
- Get **device health / reachability** and export to CSV
- Pull **SLA metrics** (latency/jitter/loss) per site

---

### References

- Cisco DevNet Sandbox: SD‑WAN Always‑On
  - https://devnetsandbox.cisco.com/DevNet/catalog/SD-WAN-Always-On_sd-wan-always-on
- Cisco SD‑WAN Authentication (Session‑based)
  - https://developer.cisco.com/docs/sdwan/authentication/#session-based-authentication
