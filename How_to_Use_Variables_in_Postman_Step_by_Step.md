# How to Use Variables in Postman (Step-by-Step)

In this tutorial, you'll replace the hard-coded base URL with a variable
so you can reuse it in multiple requests.

------------------------------------------------------------------------

## Step 1: Open Your Collection

Open the collection that contains your **Login** and **Get Devices**
requests.

------------------------------------------------------------------------

## Step 2: Create a Collection Variable

1.  Click your collection.
2.  Select the **Variables** tab.
3.  Create a new variable:

```{=html}
<!-- -->
```
    Variable: base_url
    Value: https://sandbox-sdwan-2.cisco.com

4.  Click **Save**.

------------------------------------------------------------------------

## Step 3: Update the Login Request

Replace the URL:

**Before**

    https://sandbox-sdwan-2.cisco.com/j_security_check

**After**

    {{base_url}}/j_security_check

Keep the Body as **x-www-form-urlencoded**:

    j_username = devnetuser
    j_password = RG!_Yw919_83

Click **Save**.

------------------------------------------------------------------------

## Step 4: Update the Get Devices Request

Replace the URL:

**Before**

    https://sandbox-sdwan-2.cisco.com/dataservice/device

**After**

    {{base_url}}/dataservice/device

Click **Save**.

------------------------------------------------------------------------

## Step 5: Test the Variable

1.  Send the **Login** request.
2.  Send the **Get Devices** request.

Both requests should work exactly as before.

> **Note:** Postman automatically uses the value of `{{base_url}}`
> wherever it appears in your requests.
