# How to Create and Use Environment Variables in Postman (Step-by-Step)

In this tutorial, you'll create an environment variable named `base_url` and use it in your API requests.

---

## Step 1: Create a New Environment

1. Under **Environments**, click **New Environment**.
2. Name it:
   ```
   Cisco SD-WAN Sandbox
   ```
3. Add a variable:

   | Variable | Value |
   |----------|-------|
   | base_url | https://sandbox-sdwan-2.cisco.com |

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

Keep the Body as **x-www-form-urlencoded**:

```
j_username = devnetuser
j_password = RG!_Yw919_83
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

Instead of typing the full URL in every request, you used:

```
{{base_url}}
```

Postman automatically replaces it with:

```
https://sandbox-sdwan-2.cisco.com
```

This makes your requests easier to maintain. If the server URL changes, simply update the **base_url** environment variable instead of editing every request.
