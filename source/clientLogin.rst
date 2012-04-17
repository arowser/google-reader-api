ClientLogin
===========================================
ClientLogin can be used with any application that can make an HTTPS POST request. The POST request should be structured as a form post with the default encoding application/x-www-form-urlencoded. Parameters should be included in the body of the post.
Action URL parameter: https://www.google.com/accounts/ClientLogin

Parameter Description:

**accountType**::
  Type of account to request authorization for. Possible values are 

  * GOOGLE (get authorization for a Google account only) 
  * HOSTED (get authorization for a hosted account only) 
  * HOSTED_OR_GOOGLE (get authorization first for a hosted account; if attempt fails, get authorization for a Google account)

  Use HOSTED_OR_GOOGLE if you're not sure which type of account you want authorization for. If the user information matches both a hosted and a Google account, only the hosted account is authorized.
**Email**
  User's full email address. It must include the domain (i.e. johndoe@gmail.com).
**Passwd**
  User's password.
**service**     
  Name of the Google service you're requesting authorization for. Each service using the Authorization service is assigned a name value; for example, the name associated with Google Reader is 'reader'. This parameter is required when accessing services based on Google Data APIs. For specific service names, refer to the service documentation.
**source**
  Short string identifying your application, for logging purposes. This string should take the form: "companyName  -applicationName-versionID".

ClientLogin response
In response to a login request, Google returns either an HTTP 200, if login succeeded, or an HTTP 403, if login failed.
A success response contains the authorization token, labeled "Auth", in the body of the response. Your application must reference this token in each request to the Google service for this user. Additional cookies, labeled "SID" and "LSID", are not currently active and should not be used.

Set up a mechanism to request access to a Google service.
Refer to documentation for the Google service for information on the proper request format. All requests to a Google service must include a valid authorization token. In general, a request to a Google service is in the form of an HTTP GET (or POST if writing new data), with the token referenced in the request header.

The request header should take the following form::

  Authorization: GoogleLogin auth= "Auth"

You can get more info about authentication and authorization for google APIs from url
https://code.google.com/apis/accounts/docs/GettingStarted.html
 
