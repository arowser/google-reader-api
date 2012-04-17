/tag/list
-----------

GET label list, some label is system pre-values like starred, broadcast

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - output:  json
    - ck: <timestamp>
    - client:  <application Name>

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/tag/list?output=json&ck=<timeStamp>&client=<application Name>

* response::

       {
         "tags": [
           {
             "id": "user/<usrId>/state/com.google/starred",
             "sortid": "802E94E7"
           },
           {
             "id": "user/<usrId>/state/com.google/broadcast",
             "sortid": "53F8A16B"
           },
           {
             "id": "user/<usrId>/state/com.blogger/blogger-following",
             "sortid": "CE94D1A3"
           }
         ]
       }
 
