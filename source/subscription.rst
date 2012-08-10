/subscription
-----------------

/subscription/igoogle
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET igoogle subscriptions list

* Methods::

    GET

* Authentication::

    Required.

* request parameters::

    None

* Post Data::

    None

* example::

    http://www.google.com/reader/api/0/subscription/igoogle?output=json

* response::

    {
      "subscriptions": [
        {
          "id": "feed/http://www.cnn.com/partners/google/cnn_topstories.rss",
          "title": "CNN.com",
          "categories": [],
          "firstitemmsec": "0"
        },
        {
          "id": "feed/http://adwords.blogspot.com/feeds/posts/default",
          "title": "Inside AdWords",
          "categories": [],
          "firstitemmsec": "0"
        }
      ]
    }

/subscription/edit
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Addo or remove feed to a new folder or change feed name

    http://www.google.com/reader/api/0/subscription/edit

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                   <application Name>. 
    - source:                   RECOMMENDATION: subscribe from recommandation
                                SUBSCRIBE_BUTTON: when you click Subscribe butthon

* Post Data:

    - s:    <StreamId_>
    - T:    <token>
    - ac:   subscribe: Action to perform on the given StreamId. Possible values are subscribe, unsubscribe and edit
           | unsubscribe: unsuscribe a feed
           | edit: use to add folder
    - a:    user/<usrId_>/label/good  add the subscription to (generally a user label). May be repeated to add to more than one folder 
    - t:    <feed title>

* example::

    https://www.google.com/reader/api/0/subscription/edit?source=RECOMMENDATION&client=<application Name>

* response::

    OK
 
/subscription/list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET subscriptions list

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

    https://www.google.com/reader/api/0/subscription/list?output=json&ck=<timeStamp>&client=<application Name>

* response::

    {
      "subscriptions": [
        {
          "id": "feed/http://feeds.feedburner.com/MyMicro-isv",
          "title": "47 Hats",
          "categories": [],
          "sortid": "FB039968",
          "firstitemmsec": "1252975023032"
        },
        {
          "id": "feed/http://www.amazon.com/rss/new-releases/books/5/ref=pd_nr_rss_link",
          "title": "Amazon.com: Hot New Releases in Books > Computers & Internet",
          "categories": [],
          "sortid": "77E40AE6",
          "firstitemmsec": "1262159994543"
        },
        {
          "id": "feed/http://blog.cartercole.com/feeds/posts/default?orderby=updated",
          "title": "Carter Cole's Blog",
          "categories": [],
          "sortid": "0B6626E4",
          "firstitemmsec": "1280455399985"
        },
        {
          "id": "feed/http://feed.feedsky.com/CWUfeed",
          "title": "China Web Updates",
          "categories": [],
          "sortid": "E53C4858",
          "firstitemmsec": "1252598589828"
        },
        {
          "id": "feed/http://feeds.feedburner.com/cwr",
          "title": "China Web2.0 Review",
          "categories": [],
          "sortid": "2EF2197E",
          "firstitemmsec": "1239983501546"
        }
      ]
    }
    
    
/subscription/quickadd
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Subscribe a feed, if you input a keyword, will return some feed urls include keyword, you need use https://www.google.com/reader/directory/search?q=<keyword> to get more details about search result.
The Subscription Limit is 2000.

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                    <application Name>. 

* Post Data:

    - quickadd:                 <StreamId_>
    - T: <token>

* example::

    https://www.google.com/reader/api/0/subscription/list?output=json&ck=<timeStamp>&client=<application Name>

* response::

    OK        

/subscription/export
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Export subscriptions list

* Methods::

    GET

* Authentication::

    Required.

* example::

    https://www.google.com/reader/subscriptions/export?hl=en

* response::

    A XML file named "google-reader-subscriptions.xml"
 
