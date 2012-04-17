/edit-tag
--------------
Add star/like/ for item
Yoc can use this method to add tag for ite,
add label
add start
share item
add like
set item read

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                    <application Name>. 

* Post Data:

    - quickadd:                 feedurl
    - T: <token>
    - a:       user/<usrId_>/state/com.google/starred
             | user/<usrId_>/state/com.google/like
             | user/<usrId_>/state/com.google/broadcast
             | user/<usrId_>/label/test
             | user/<usrId_>/state/com.google/read
             | user/<usrId_>/state/com.google/kept-unread
             | user/<usrId_>/state/com.google/dislike
             | user/<usrId_>/state/com.google/tracking-kept-unread

    - r:        user/<usrId_>/state/com.google/like
    - async:   true
    - s:       feed/<feed url>
            |  user/<usrId_>/source/com.google/bundle-item
    - i:       tag:google.com,2005:reader/item/6b200817c3671b67

* example::

    https://www.google.com/reader/api/0/subscription/list?output=json&ck=<timeStamp>&client=<application Name>

* response::

       {
         "query": "http://tsd.blogspot.com/feeds/posts/default",
         "numResults": 1,
         "streamId": "feed/http://tsd.blogspot.com/feeds/posts/default"
       }
              

Another method .

* Methods::

    GET

* Authentication::

    Required.

* request parameters:

    - i:    2104361263645647706
    - a:     user/<usrId_>/state/com.google/starred
    - T: <token>
    - R:      https://www.google.com/reader/m/view/feed/http://feeds.feedburner.com/comscoreblog?hl=en&i=2104361263645647706&c=CNCM1_-3k6wC&n=1

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/edit-tag?i=2104361263645647706&a=user/<usrId_>/state/com.google/starred&T=//0cDo0KKUdeW2aPzoCxsDCA&R=https://www.google.com/reader/m/view/feed/http://feeds.feedburner.com/comscoreblog?hl=en&i=2104361263645647706&c=CNCM1_-3k6wC&n=1

* response::

    Redirect to R point to URL.
 
