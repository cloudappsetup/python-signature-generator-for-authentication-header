This module can help you generate the signature that you need to pass in the header when making PayPal API calls on someone else's behalf using the Permissions API. You can find some commented-out example code for using the module in genPermissionsAuthHeader.py starting at line 63. Here is a quick summary of the steps you need to perform to use this module:

- Install the module in your Python run-time (one way to do so is to copy the org directory under the site-packages directory)
- In your code: import genPermissionsAuthHeader from org.paypalx
- Invoke the method to generate the signature: genPermissionsAuthHeader(apiUser="YourApiuser_api1.paypal.com", apiPass="YourApiPasswd", accessTok="accessToken", secTok="tokenSecret", httpMethod="POST", scriptURI="https://api-3t.sandbox.paypal.com/nvp")
  - Please refer to the Permissions API document to determine the meaning of the specific parameters and how you should obtain them.
- The method returns a timeStamp and the signature as a tuple: pass them in the header of the API call as follows: X-PP-AUTHORIZATION=timestamp="timeStamp",token="accessToken",signature="signature"

Please post additional questions in the Permissions forum at www.x.com or open a DTS ticket.
