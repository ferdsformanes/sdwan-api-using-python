How to Retrieve the List of Fabric Devices in Cisco ACI Using Postman

Step 1: Log in to the APIC

Create a POST request:

```
https://sandboxapicdc.cisco.com/api/aaaLogin.json
```

Go to Body → raw → JSON, then enter:

```json
{
  "aaaUser": {
    "attributes": {
      "name": "admin",
      "pwd": "ciscopsdt"
    }
  }
}
```

Click Send.

────────

Step 2: Get the Fabric Devices

Create a GET request:

```
https://sandboxapicdc.cisco.com/api/node/class/fabricNode.json
```

Click Send.

────────

Step 3: View the Results

The response contains the list of fabric devices, including:

• Device name
• Node ID
• Role (Leaf or Spine)
• Model
• Serial number
• Software version
• Management IP address

This guide assumes you’re using the Cisco DevNet ACI Sandbox and that Postman automatically reuses the authentication cookie from the login request.