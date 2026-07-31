# How to Make Your First API Call in Postman (Step-by-Step)

In this tutorial, you'll configure a **Login** request to authenticate
with the Cisco SD-WAN DevNet Sandbox and then send a **Get Devices**
request to retrieve the device inventory.

## Step 1: Open Your Collection

Open your **Cisco SD-WAN APIs** collection.

You should have the following requests:

-   Login
-   Get Devices

## Step 2: Configure the Login Request

Open the **Login** request.

Set the request method to:

``` text
POST
```

Set the request URL to:

``` text
https://sandbox-sdwan-2.cisco.com/j_security_check
```

## Step 3: Add the Request Body

Click the **Body** tab.

Select **x-www-form-urlencoded**.

Add the following parameters:

  Key          Value
  ------------ ---------------
  j_username   devnetuser
  j_password   RG!\_Yw919_83

## Step 4: Send the Login Request

Click **Send**.

If the login is successful, Postman stores the session cookie
(**JSESSIONID**) automatically.

## Step 5: Configure the Get Devices Request

Open the **Get Devices** request.

Set the request method to:

``` text
GET
```

Set the request URL to:

``` text
https://sandbox-sdwan-2.cisco.com/dataservice/device
```

## Step 6: Send the Request

Click **Send**.

If authentication was successful, Postman returns a JSON response
containing the list of Cisco SD-WAN devices.

## That's It!

You have successfully authenticated with the Cisco SD-WAN DevNet Sandbox
and made your first API call using Postman. In the next tutorial, we'll
explore the JSON response and learn how to read the data returned by the
API.
