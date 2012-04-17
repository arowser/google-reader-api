/unread-count
--------------
GET unread item count about feeds, auto update one hour, or status change. 

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - allcomments     true
    - autorefresh     2 (auto refresh times, auto increase when update)
    - output          json
    - ck              1319791038205
    - client          <application Name>


* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/unread-count?allcomments=true&autorefresh=2&output=json&ck=<timeStamp>&client=<application Name>

* response::

      {
        "max": 1000,
        "unreadcounts": [
          {
            "id": "feed/http://discuss.joelonsoftware.com/default.asp?pg=pgRss&ixDiscussGroup=5",
            "count": 53,
            "newestItemTimestampUsec": "1319741529426196"
          }
        ]
      }     
 
