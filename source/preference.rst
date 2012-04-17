/preference
----------------
The api for reader settings.

/set
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                    <application Name>. 

* Post Data:

    - k       custom-favicons-enabled
          |   is-card-view  list or expand item
          |   read-items-visible: read new item
          |   shown-no-social-introduction
          |   show-first-like-bubble
          |   show-first-share-bubble
    - v       false/true

    - k        lhn-prefs
    - v        {"selectors":{"ism":"true"},"recommendations":{"ism":"true"},"subscriptions":{"ism":"false"},"friends":{"ism":"false"}}
             | {"selectors":{"ism":"true"},"recommendations":{"ism":"true"},"subscriptions":{"ism":"false","suc":"false"},"friends":{"ism":"true"}}
             | {"selectors":{"ism":"false"},"recommendations":{"ism":"true"},"subscriptions":{"ism":"false","suc":"true","ssa":"false","sas":"false"},"friends":{"ism":"true"}}
             
    - ism:
             false expand item 
             true list item 
    - suc: 
            true show unread count
            false show unread count
    - ssa: 
            true sort by alphabetically
            false sort by drag and drop
    - sas: 
            true show all
            false show update
    - saf: 
            true TODO
    - sfa: 
            true TODO
    - T       <token>

* example::

    https://www.google.com/reader/api/0/preference/set?client=<application Name>  set the first like item

* response::

     OK

/stream/list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get preference stream list.

* Methods::

    GET

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                    <application Name>. 

* Post Data:

    None

* example::

    https://www.google.com/reader/api/0/preference/stream/list?output=json

* response::

    {
      "streamprefs": {
        "splice/feed/http://blog.neildavidson.com/atom.xml|feed/http://www.torry.net/apps.rss|feed/http://planet-microisv.com/rss20.xml|feed/http://www.alwinhoogerdijk.com/feed/": [
          {
            "id": "is-expanded",
            "value": "false"
          }
        ],
        "user/14868016043292606801/state/com.google/self": [
          {
            "id": "is-expanded",
            "value": "true"
          }
        ],
        "pop/topic/top/language/en": [
          {
            "id": "ranking",
            "value": "auto"
          }
        ],
        "pop/feed-recommendations/prefs": [
          {
            "id": "is-expanded",
            "value": "true"
          },
          {
            "id": "ranking",
            "value": "oldest"
          }
        ],
        "splice/feed/http://dn.codegear.com/rss|feed/http://discuss.joelonsoftware.com/default.asp?pg=pgRss&ixDiscussGroup=3|feed/http://blog.wangbin1979.com/index.atom|feed/http://blogs.zdnet.com/Google/wp-rss2.php": [
          {
            "id": "is-expanded",
            "value": "false"
          }
        ],
        "pop/topic/top/language/en": [
          {
            "id": "ranking",
            "value": "oldest"
          }
        ],
        "feed/http://www.codeproject.com/webservices/articlerss.aspx?cat=1": [
          {
            "id": "ranking",
            "value": "auto"
          }
        ],
        "user/14868016043292606801/state/com.google/root": [
          {
            "id": "subscription-ordering",
            "value": "0B17F6532EF2197EFFFF20473850ED4BB997905904688E0854B353180139D260D3542E8DC973959A8F44211E350E0AE22BDFCCED73355E7BFE1C38A725AC6A90904335982448AA1A078E88B5BF89AFC6DE063CBAF6AAF91D6A3ECB6079F97D51380237A12DB8A8509961A9752307B678D1B9B28F426923ED0491FF94572F5C4F22E0DA4AEE0CA667E390AB6D6E1D1CBF31FE26C6BF6F7D3F397BA136DC83580D4518880CDFE73514ABB582FC387CDD5E1FDBD7ACFB039968C5AAC3F9E53C485884F120DBB10327068607387FBAF2C951"
          }
        ],
        "feed/http://feed.web20share.com/": [
          {
            "id": "ranking",
            "value": "auto"
          }
        ]
      }
    }    
 
/stream/set
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Set items sort method

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:                    <application Name>. 

* Post Data:

    - s:     <StreamId_>
    - T:     <token>

    - k:     ranking
    - v:     [auto|newest|oldest]

    - k:     is-translated
    - v:     false

    - k:     start-page
    - v:     <StreamId_>

    - k:     show-poptart-stream-interruption
    - v:     false

* example::

    https://www.google.com/reader/api/0/preference/stream/set?client=<application Name>

* response::

    OK

/list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET preferenct setting lists

* Methods::

    GET

* Authentication::

    Required.

* request parameters:

    - output:  json
    - ck: <timestamp>
    - client:  settings

* example::

    https://www.google.com/reader/api/0/preference/list?output=json&ck=<timeStamp>&client=settings

* response::

    {
      "prefs": [
        {
          "id": "queue-sorting",
          "value": "date"
        },
        {
          "id": "read-items-visible",
          "value": "false"
        },
        {
          "id": "design",
          "value": "scroll"
        },
        {
          "id": "show-all-tree-items",
          "value": "true"
        },
        {
          "id": "is-card-view",
          "value": "false"
        },
        {
          "id": "show-minimized-navigation",
          "value": "false"
        },
        {
          "id": "show-oldest-interrupt",
          "value": "true"
        },
        {
          "id": "show-scroll-help",
          "value": "false"
        },
        {
          "id": "scroll-tracking-enabled",
          "value": "true"
        },
        {
          "id": "shuffle-token",
          "value": "-7687012637471574035"
        },
        {
          "id": "start-page",
          "value": "home"
        },
        {
          "id": "display-lang",
          "value": ""
        },
        {
          "id": "custom-favicons-enabled",
          "value": "true"
        },
        {
          "id": "blogger-following-opt-out",
          "value": "false"
        },
        {
          "id": "show-blogger-following-intro",
          "value": "true"
        },
        {
          "id": "show-search-clarification",
          "value": "true"
        },
        {
          "id": "friends-v3",
          "value": "true"
        },
        {
          "id": "friends-v3-upsell",
          "value": "true"
        },
        {
          "id": "show-first-share-bubble",
          "value": "false"
        },
        {
          "id": "commented-items-only",
          "value": "true"
        },
        {
          "id": "mobile-start-page",
          "value": ""
        },
        {
          "id": "mobile-num-entries",
          "value": "9"
        },
        {
          "id": "mobile-links-same-window",
          "value": "false"
        },
        {
          "id": "confirm-mark-as-read",
          "value": "false"
        },
        {
          "id": "tree-alpha-sort",
          "value": "false"
        },
        {
          "id": "custom-item-links",
          "value": "{}"
        },
        {
          "id": "lhn-prefs",
          "value": "{"subscriptions":{"ism":"false","suc":"true"},"selectors":{"ism":"false"},"recommendations":{"ism":"false"},"friends":{"ism":"false"}}"
        },
        {
          "id": "show-first-like-bubble",
          "value": "false"
        },
        {
          "id": "show-non-friend-likes",
          "value": "true"
        },
        {
          "id": "use-public-username",
          "value": "true"
        },
        {
          "id": "mobilescroll-num-entries",
          "value": "15"
        },
        {
          "id": "broadcast-friends-interruption-minimized",
          "value": "false"
        },
        {
          "id": "show-poptart-stream-interruption",
          "value": "true"
        },
        {
          "id": "use-poptart-stream-as-welcome-page",
          "value": "false"
        },
        {
          "id": "show-fallback-poptart-stream",
          "value": "true"
        },
        {
          "id": "show-explore-welcome-page",
          "value": "true"
        },
        {
          "id": "broadcast-friends-opt-out",
          "value": "false"
        },
        {
          "id": "public-comments-acl-migrated",
          "value": "true"
        },
        {
          "id": "public-comments-acl-chosen",
          "value": "true"
        },
        {
          "id": "unsupported-browser-warning-last-shown",
          "value": "0"
        },
        {
          "id": "shown-no-social-introduction",
          "value": "true"
        }
      ]
    }
    
    
 
