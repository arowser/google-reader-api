/token
--------
A token is a special 57 chars string that is used like a session identification, but that expire rather quickly. You usaully need a token for direct api calls that change informations.

Token use to protect against XSRF attacks, all state-changing methods require an action token in addition to an authentication token. The token can be fetched by making a GET request for /reader/api/0/token and should be passed in to state-changing requests (generally POST requests) with the T parameter
The token is valid for 30 minutes. If it is missing or invalid, a 401 HTTP response code will be given and the response will have a X-Reader-Google-Bad-Token: true HTTP header.

* Methods::

    GET

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                    <application Name>. 

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/token?ck=<timeStamp>&client=<application Name>

* response::

    //GpF9xMPOqgfZ4roMSpjpUQ
 
