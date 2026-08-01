# How to Create and Use Environment Variables in Postman (Step-by-Step)

In this tutorial, you'll create environment variables and use them in your API requests.

---

## Step 1: Create a New Environment

1. Under **Environments**, click **New Environment**.
2. Name it:
   ```
   Cisco SD-WAN Sandbox
   ```
3. Add these variables:

| Variable | Value |
|----------|-------|
| base_url | https://sandbox-sdwan-2.cisco.com |
| username | devnetuser |
| password | RG!_Yw919_83 |

4. Click **Save**.

---

## Step 2: Select the Environment

From the Environment dropdown in the top-right corner, select:

```
Cisco SD-WAN Sandbox
```

---

## Step 3: Update the Login Request

Replace the URL:

**Before**
```
https://sandbox-sdwan-2.cisco.com/j_security_check
```

**After**
```
{{base_url}}/j_security_check
```

Keep the Body as **x-www-form-urlencoded** and replace the hard-coded values:

**Before**
```
j_username = devnetuser
j_password = RG!_Yw919_83
```

**After**
```
j_username = {{username}}
j_password = {{password}}
```

Click **Save**.

---

## Step 4: Update the Get Devices Request

Replace the URL:

**Before**
```
https://sandbox-sdwan-2.cisco.com/dataservice/device
```

**After**
```
{{base_url}}/dataservice/device
```

Click **Save**.

---

## Step 5: Test the Requests

1. Send the **Login** request.
2. Send the **Get Devices** request.

Both requests should work exactly as before.

---

## What Happened?

Instead of hard-coding the server URL and login credentials, you stored them as environment variables:

```
{{base_url}}
{{username}}
{{password}}
```

Postman automatically replaces these variables with their values from the active environment. If the server URL or credentials change, simply update the environment variables instead of editing every request.
