/stream
--------
/contents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
/user
'''''''''''''''''''''''''''''''''''''''''''

GET reader user item, share/starred/ reading-list
Lists all items from a given label.

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - co:     true
    - c:       CKL2t6j30KICSPTQ3f2hhawC
    - n:       40
    - ck: <timestamp>
    - client:  <application Name>

* Post Data::

    None

* example:

    List all items that the user has chosen to share public
        https://www.google.com/reader/api/0/stream/contents/user/<usrId>/state/com.google/broadcast-friends-comments?co=true&c=CKL2t6j30KICSPTQ3f2hhawC&n=40&ck=<timeStamp>&client=<application Name>
    
    List all items that the user has marked as "starred"
        https://www.google.com/reader/api/0/stream/contents/user/<usrId>/state/com.google/starred?n=20&ck=<timeStamp>&client=<application Name>
    
    List all items in the user's reading list. This is a list of all of the items from all of the user's feeds, excluding items depending on the xt (exclude target) parameter.
        https://www.google.com/reader/api/0/stream/contents/user/<usrId>/state/com.google/reading-list?ot=1317009600&r=n&xt=user/<usrId>/state/com.google/read&n=20&ck=<timeStamp>&client=<application Name>
    
    Lists all items from a given label.
        http://www.google.com/reader/api/0/stream/contents/user/-/label/label?ot=1253066400&r=n&xt=user/-/com.google/read&n=20&ck=<timeStamp>&client=<application Name>
    
    List all notes that the user has created.
        http://www.google.com/reader/api/0/stream/contents/user/-/state/com.google/created?n=20&ck=<timeStamp>&client=<application Name>

* response::

      {
        "id": "user/01723985652832499840/source/com.google/post",
        "title": ""post" via iamaelephant in Google Reader",
        "self": [
          {
            "href": "http://www.google.com/reader/api/0/stream/contents/user/01723985652832499840/state/com.google/created?n=20&ck=1255661572704&client=<application Name>"
          }
        ],
        "author": "iamaelephant",
        "updated": 1255661564,
        "items": [
          {
            "crawlTimeMsec": "1255661564095",
            "id": "tag:google.com,2005:reader/item/2dc5e875a623fe5e",
            "categories": [
              "user/01723985652832499840/source/com.google/post",
              "user/01723985652832499840/state/com.google/broadcast",
              "user/01723985652832499840/state/com.google/read",
              "user/01723985652832499840/state/com.google/fresh"
            ],
            "published": 1255661564,
            "updated": 1255661564,
            "related": [
              {
                "href": "http://www.google.com/reader/shared/01723985652832499840",
                "streamId": "user/01723985652832499840/state/com.google/broadcast"
              }
            ],
            "alternate": [
              {
                "href": "http://www.google.com/reader/item/tag:google.com,2005:reader/item/2dc5e875a623fe5e",
                "type": "text/html"
              }
            ],
            "content": {
              "direction": "ltr",
              "content": "this is the note text"
            },
            "author": "iamaelephant",
            "likingUsers": [],
            "comments": [],
            "annotations": [],
            "origin": {
              "streamId": "user/01723985652832499840/source/com.google/post",
              "htmlUrl": "http://www.google.com/reader/shared/01723985652832499840"
            }
          }
        ]
      }

/feed
'''''''''''''''''''''''''''''''''''''''''''
GET items belonging to a particular feed.

* Path::

    http://www.google.com/reader/stream/contents/feed

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - r:       n [d|n|o]  Sort order of item results. d or n gives items in descending date order, o in ascending order.
    - n:       20
    - ck: <timestamp>
    - client:  <application Name>
    - ot:      1317200400(optional)  The time from which you want to retrieve items. Only items that have been crawled by Google Reader after this time will be returned.
    - xt:      user/<usrId_>/state/com.google/read
    - likes:   false
    - comments:      false

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/stream/contents/feed/<feedurl>
    https://www.google.com/reader/api/0/stream/contents/feed/http://tsd.blogspot.com/feeds/posts/default?r=n&n=20&ck=<timeStamp>&client=<application Name>

* response::
    
    {
      "direction": "ltr",
      "id": "feed/http://tsd.blogspot.com/feeds/posts/default",
      "title": "Suzy&#39;s Blog",
      "description": "First tryout of Blogger.",
      "self": [
        {
          "href": "https://www.google.com/reader/api/0/stream/contents/feed/http://tsd.blogspot.com/feeds/posts/default?r=n&n=20"
        }
      ],
      "alternate": [
        {
          "href": "http://tsd.blogspot.com/",
          "type": "text/html"
        }
      ],
      "updated": 1250101187,
      "items": [
        {
          "isReadStateLocked": true,
          "crawlTimeMsec": "1250101187715",
          "timestampUsec": "1250101187715811",
          "id": "tag:google.com,2005:reader/item/0511d1c926f96565",
          "categories": [
            "user/14868016043292606801/state/com.google/reading-list",
            "user/14868016043292606801/state/com.google/read"
          ],
          "published": 988907100,
          "updated": 988907184,
          "alternate": [
            {
              "href": "http://tsd.blogspot.com/2001_04_29_archive.html#3480863",
              "type": "text/html"
            }
          ],
          "content": {
            "direction": "ltr",
            "content": "Testing testing 1 2 3.<div><img width="1" height="1" src="https://blogger.googleusercontent.com/tracker/3020819-3480863?l=tsd.blogspot.com" alt=""></div>"
          },
          "author": "Suzy",
          "likingUsers": [],
          "comments": [],
          "annotations": [],
          "origin": {
            "streamId": "feed/http://tsd.blogspot.com/feeds/posts/default",
            "title": "Suzy&#39;s Blog",
            "htmlUrl": "http://tsd.blogspot.com/"
          }
        }
      ]
    }

/details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

GET a feed details like subscribers, velocity.

* Path::

    http://www.google.com/reader/stream/details

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - s:       user/03125399518623059338/state/com.google/broadcast
    - tz:      480
    - fetchTrends:     false(Trend chart info named trendsCharts will return when you set ture)
    - output:  json
    - ck: <timestamp>
    - client:  <application Name>

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/stream/details?s=feed/http://www.codeproject.com/webservices/articlerss.aspx?cat=1&tz=480&fetchTrends=false&output=json&ck=<timeStamp>&client=<application Name>

* response::
  
    {
      "subscribers": "29,760",
      "velocity": "63.0",
      "successfulCrawlTimeUsec": "1320026750404957",
      "failedCrawlTimeUsec": "1319316732501055",
      "lastFailureWasParseFailure": false,
      "trendsCharts": {},
      "feedUrl": "http://www.codeproject.com/webservices/articlerss.aspx?cat=1"
    }
    
/items
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

/ids
'''''''''''''''''''''''''''''''''''''''''''
Given one or more StreamIds and fetching options, returns the IDs of the items in those Streams. Getting just item IDs is significantly cheaper than getting stream contents. If you need to do filtering of items, it is highly encouraged to do this at the ID level before fetching item contents for the subset of items that remain.

* Path::

    http://www.google.com/reader/stream/items/ids

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:
    - s:       splice/<StreamId>|<StreamId>|<StreamId>
    - ot:      1317002400
    - r:       a
    - xt:      user/<usrId_>/state/com.google/dislike
    - n:       1000
    - merge:   true
    - output:  json
    - ck: <timestamp>
    - client:  <application Name>
    - includeAllDirectStreamIds trueS (If true, all direct StreamIds will be included in the response. If false, feed StreamIds will not be included)

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/stream/items/ids?s=splice/feed/http://www.adsenser.org/rss.php|feed/http://codebetter.com/blogs/MainFeed.aspx|feed/http://www.theserverside.com/rss/theserverside-rss2.xml|feed/http://feeds.feedburner.com/DanweiRss10|pop/topic/top/language/en&ot=1317002400&r=a&xt=user/<usrId>/state/com.google/dislike&n=1000&merge=true&output=json&ck=<timeStamp>&client=<application Name>

    https://www.google.com/reader/api/0/stream/items/ids?s=pop/topic/top/language/en&ot=1317002400&r=a&xt=user/<usrId>/state/com.google/dislike&n=1000&merge=true&output=json&ck=<timeStamp>&client=<application Name>

* response::

       {
         "itemRefs": [
           {
             "id": "-7478575264030238688",
             "directStreamIds": [],
             "timestampUsec": "1319455503345959"
           },
           {
             "id": "3984695045297823254",
             "directStreamIds": [],
             "timestampUsec": "1320021476284225"
           }
         ]
       }
       
/count
'''''''''''''''''''''''''''''''''''''''''''
1.Since July 8, 2009 you have read a total of 3,807 items.

* Path::

    http://www.google.com/reader/stream/items/count

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - s:       user/<usrId_>/state/com.google/read
    - a:       true
    - ck: <timestamp>
    - client:  <application Name>

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/stream/items/count?s=user/<usrId>/state/com.google/read&a=true&ck=<timeStamp>&client=<application Name>

* response::

    3,807#July 8, 2009

2.get you like items count

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - s:       user/<usrId_>/state/com.google/like
    - a:       false
    - ck: <timestamp>
    - client:  <application Name>

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/stream/items/count?s=user/<usrId>/state/com.google/like&a=false&ck=<timeStamp>&client=<application Name>

* response::

    10
    
/contents
'''''''''''''''''''''''''''''''''''''''''''
GET some items content

* Path::

    http://www.google.com/reader/stream/items/contents

* Methods::

    POST 

* request parameters:

    - freshness:   false
    - likes:       false
    - comments:    flase
    - ck: <timestamp>
    - client:      <application Name>
    - hl:          en 

* Post Data:

    - i:  5495123609939060429 item id
    - i:  3984695045297823254 repeat the i parameter to get multiple item contents
    - it:  1319682914801805  timestampUsec
    - it:  1319693811042080
    - indexs:  0
    - rs:  pop/topic/top/language/en
    - trans:  true (only use when need trans to my language)
    - T: <token>

* example::

    https://www.google.com/reader/api/0/stream/items/contents?freshness=false&ck=<timeStamp>&client=<application Name>

* response::

    {
      "direction": "ltr",
      "id": "feed/http://www.fastspring.com/blog/feed/",
      "title": "The FastSpring E-Commerce Blog",
      "description": "Insights into e-commerce, marketing, &amp; software, plus FastSpring news.",
      "self": [
        {
          "href": "https://www.google.com/reader/api/0/stream/items/contents?freshness=false&likes=false&comments=false&ck=1321240780707&client=scroll"
        }
      ],
      "alternate": [
        {
          "href": "http://www.fastspring.com/blog",
          "type": "text/html"
        }
      ],
      "updated": 1320285094,
      "items": [
        {
          "crawlTimeMsec": "1320285094345",
          "timestampUsec": "1320285094345931",
          "id": "tag:google.com,2005:reader/item/f7e6ecc214bd1875",
          "categories": [
            "FastSpring Info",
            "News"
          ],
          "title": "New FastSpring Demo Movie Released",
          "published": 1320269596,
          "updated": 1320269596,
          "alternate": [
            {
              "href": "http://www.fastspring.com/blog/2011/11/new-fastspring-demo-movie-released/",
              "type": "text/html"
            }
          ],
          "content": {
            "direction": "ltr",
            "content": "......"
          },
          "author": "Dan",
          "likingUsers": [],
          "comments": [],
          "annotations": [],
          "origin": {
            "streamId": "feed/http://www.fastspring.com/blog/feed/",
            "title": "The FastSpring E-Commerce Blog",
            "htmlUrl": "http://www.fastspring.com/blog"
          }
        }
      ]
    }
 
