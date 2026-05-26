# Cisco Catalyst Center – First API Call Using Postman (Step-by-Step Guide)

## ✅ Step 0 — What you need
- Postman installed  
- Access to Cisco Catalyst Center (or DevNet Sandbox)

Example:
```
https://sandboxdnac.cisco.com
```

---

## ✅ Step 1 — Configure Postman
1. Open Postman
2. Go to Settings (⚙️)
3. Turn OFF:
   - SSL Certificate Verification

---

## ✅ Step 2 — Base URL
```
https://<IP_ADDRESS>/dna/intent/api
```

Example:
```
https://sandboxdnac.cisco.com/dna/intent/api
```

---

## ✅ Step 3 — Get Auth Token

### Request
- Method: POST
- URL:
```
https://sandboxdnac.cisco.com/dna/system/api/v1/auth/token
```

### Authorization
- Type: Basic Auth
- Username: devnetuser
- Password: Cisco123!

### Headers
```
Content-Type: application/json
```

### Response
```
{
  "Token": "your_token_here"
}
```

---

## ✅ Step 4 — Call API (Get Devices)

### Request
- Method: GET
- URL:
```
https://sandboxdnac.cisco.com/dna/intent/api/v1/network-device
```

### Headers
```
X-Auth-Token: your_token_here
Content-Type: application/json
```

### Response Example
```
{
  "response": [
    {
      "hostname": "switch1",
      "managementIpAddress": "10.x.x.x"
    }
  ]
}
```

---

## ✅ Summary
- Authenticate → Get token
- Use token → Call APIs
- APIs use JSON + REST (GET/POST/PUT/DELETE)
