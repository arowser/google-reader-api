/bundle
===========================================
https://www.google.com/reader/bundle/user/<usrId_>/bundle/test

 
 /list-user-bundle
-------------------
GET usr bundle lists

* Methods::

    GET 

* Authentication::

    Required.

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/list-user-bundle?output=json&ck=1320816328167&client=scroll&hl=en

* response::

    {
      "bundles": [
        {
          "id": "user/<usrId>/bundle/title",
          "title": "title",
          "description": "description",
          "feeds": [
            {
              "id": "feed/http://www.codeproject.com/webservices/articlerss.aspx?cat=1",
              "title": "codeproject"
            },
            {
              "id": "feed/http://www.freedownloadscenter.com/Reviews.XML",
              "title": "Free Downloads Center"
            }
          ],
          "subscriberCount": "-1"
        }
      ]
    }    

/edit-bundle
-----------------
creteat bundle

* Methods::

     POST

* Authentication::

   Required.

* Post Data:

  - bundle:  user/<usrId_>/bundle/test
  - title:   title string
  - desc:    description
  - share:   false
  - streams: <streamId_>
  - streams: <streamId_> repeated to add to bundle more than one streamId
  - streams: <streamId_>
  - T:       <token>

* example::

    https://www.google.com/reader/api/0/edit-bundle?client=scroll&hl=en

* response::

    A html page

/get-bundle
---------------

* Methods::

   GET

* Authentication::

   Required.

* request parameters:

  - bundleId        user/<usrId_>/bundle/test
  - fetchAuthor:     false
  - output:  json
  - ck:      <timestamp>
  - client:  <application Name>
 
* Post Data::

    None

* example::

     https://www.google.com/reader/api/0/get-bundle?bundleId=user/<usrId>/bundle/test&fetchAuthor=false&output=json&ck=<timeStamp>&client=<application Name>

* response::

   {"bundles":[]}

 
/delete-bundle
-----------------
* Methods::

   POST

* Authentication::

   Required.

* request parameters:

    None
 
* Post Data:

  - bundleId        user/<usrId_>/bundle/test
  - T:     <token>

* example::

     https://www.google.com/reader/api/0/delete-bundle?client=<application Name>

* response::

   A html page


/bundles
--------------------------
Get bundles.

* Methods::

   GET

* Authentication::

   Required.

* request parameters:

    None
 
* example::

     https://www.google.com/reader/api/0/bundles?output=json

* response::

    {
      "bundles": {
        "news": {
          "id": "news",
          "title": "News",
          "isadded": false,
          "subscriptions": [
            {
              "id": "feed/http://newsrss.bbc.co.uk/rss/newsonline_world_edition/front_page/rss.xml",
              "title": "BBC News - World Edition"
            },
            {
              "id": "feed/http://news.google.com/?topic=h&num=3&output=rss",
              "title": "Google News"
            },
            {
              "id": "feed/http://www.sfgate.com/rss/feeds/news.xml",
              "title": "SFGate: Top News Stories"
            },
            {
              "id": "feed/http://www.bizjournals.com/rss/feed/daily/sanfrancisco",
              "title": "San Francisco Business News - Local San Francisco News | The San Francisco Business Times"
            },
            {
              "id": "feed/http://www.sfist.com/index.rdf",
              "title": "SFist"
            },
            {
              "id": "feed/http://www.nytimes.com/services/xml/rss/nyt/HomePage.xml",
              "title": "New York Times"
            },
            {
              "id": "feed/http://www.mv-voice.com/feed/rss.php",
              "title": "Mountain View Voice"
            },
            {
              "id": "feed/http://abclocal.go.com/kgo/xml?id=3242447",
              "title": "ABC7 News: Bay Area Online News (San Francisco, Oakland, San Jose)"
            },
            {
              "id": "feed/http://www.guardian.co.uk/rssfeed/0,,1,00.xml",
              "title": "Guardian.co.uk"
            }
          ],
          "isfeatured": true
        }
      }
    }


/list-friends-bundle
--------------------------
List your friends bundles.

* Methods::

   GET

* Authentication::

   Required.

* request parameters:

    None
 
* example::

     https://www.google.com/reader/api/0/list-friends-bundle?output=json
 
* response:

   Same output with `/bundles`_

/list-featured-bundle
--------------------------
Get feature bundle lists.

* Methods::

   GET

* Authentication::

   Required.

* request parameters:

    None
 
* example::

     https://www.google.com/reader/api/0/list-featured-bundle?output=json
 
* response:

   Same output with `/bundles`_ 
 
