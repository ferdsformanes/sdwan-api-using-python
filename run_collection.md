Run a Collection

Click your collection.

Click Run.

Select the requests:
✓ Login
✓ Get Devices

Run type
✓ Functional

Run method
✓ Local

Iterations
1

Settings
✓ Persist responses for a session
✓ Stop run if an error occurs
✓ Keep variable values
✓ Save cookies after collection run

Click Start run.

Verify that:
✓ Login returns Status: 200
✓ Get Devices returns Status: 200

Note: Postman runs the requests in the order they appear in the collection. The Login request runs first, allowing the Get Devices request to automatically use the JSESSIONID cookie.
