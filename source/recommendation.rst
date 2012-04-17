 /recommendation/edit
---------------------------
Delete a feed from recommend lists.

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - client:                   <application Name>. 

* Post Data:

    - action:  dismiss
    - s       feed/http://blog.sina.com.cn/rss/twocold.xml
    - impression:      1319790434514001
    - T: <token>

* example::

    https://www.google.com/reader/api/0/recommendation/edit?client=scroll&hl=en

* response::

    OK


/recommendation/list
---------------------------

GET Google Recommended feeds for you:

* Methods::

    GET 

* Authentication::

    Required.

* request parameters:

    - output:  json
    - n:   6

* Post Data::

    None

* example::

    http://www.google.com/reader/api/0/recommendation/list?n=6&output=json

* response::

     {
       "recs": [
         {
           "title": "Antair Blog",
           "snippet": "",
           "streamId": "feed/http://www.antair.com/blog/feed/",
           "impressionTime": "1320050331402000"
         },
         {
           "title": "www.web2asia.com Blog Feed",
           "snippet": "Blog Feed",
           "streamId": "feed/http://feeds.feedburner.com/web2asia",
           "impressionTime": "1320050331402000"
         }
       ]
     }    
 
