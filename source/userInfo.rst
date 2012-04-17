/user-info
------------
GET information on the current user

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

    https://www.google.com/reader/api/0/user-info?&ck=<timeStamp>&client=<application Name>

* response::

       {
         "userId": "<usrId>",
         "userName": "test",
         "userProfileId": "110773284060173603999",
         "userEmail": "arowser@gmail.com",
         "isBloggerUser": false,
         "signupTimeSec": 1174115257,
         "isMultiLoginEnabled": true
       }
 
