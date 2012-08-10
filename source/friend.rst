/friend
--------
/friend/groups
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET reader groups.

* Methods::

    GET

* Path::

    https://www.google.com/reader/api/0/friend/groups

* request parameters:

    - client:  <application Name>
    - ck      1319594872083

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/friend/groups?output=json&ck=<timeStamp>&client=<application Name>

* response::

       {
         "sharingGroups": [
           {
             "groupId": "2",
             "isReadOnly": true,
             "name": "CONTACTS",
             "isSharing": false
           },
           {
             "groupId": "15",
             "isReadOnly": false,
             "name": "COWORKERS",
             "isSharing": false
           },
           {
             "groupId": "13",
             "isReadOnly": false,
             "name": "FRIENDS",
             "isSharing": false
           },
           {
             "groupId": "14",
             "isReadOnly": false,
             "name": "FAMILY",
             "isSharing": false
           }
         ]
       }

/friend/acl
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Methods::

    GET

* Path::

    https://www.google.com/reader/api/0/friend/acl

* request parameters:

    - output:        json
    - client:  <application Name>
    - ck      1319594872083

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/friend/acl?output=json&ck=<timeStamp>&client=<application Name>

* response::

    {
      "type": "PUBLIC",
      "memberId": [],
      "isEditingDisabled": false
    }   
        
/friend/edit
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Follow or unfollow people

* Methods::

    GET

* Path::

    https://www.google.com/reader/api/0/friend/edit

* request parameters:

    - client:  <application Name>

* Post Data:

    - action:  hidefollowing
             | removefollowing
             | addfollowing
    - u:       03125399518623059338

* example::

    https://www.google.com/reader/api/0/friend/edit?client=<application Name>

* response::

    OK

/friend/list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET you following people or followers, when you open google reader, it will get following people for every hours.

* Path::

    https://www.google.com/reader/api/0/friend/list

* Methods::

    GET

* request parameters:

    - lookup:  FOLLOWING
    - output:  json
    - ck      1319794036488
    - client:  <application Name>

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/friend/list?lookup=FOLLOWING&lookup=FOLLOWERS&output=json&ck=<timeStamp>&client=<application Name>
    https://www.google.com/reader/api/0/friend/list?lookup=FOLLOWING&output=json&ck=<timeStamp>&client=<application Name>

* response::

     {
       "friends": [
         {
           "userIds": [
             "<usrId>"
           ],
           "profileIds": [
             "110773284060173603999"
           ],
           "contactId": "3595238609574409666",
           "stream": "user/<usrId>/state/com.google/broadcast",
           "flags": 544,
           "types": [
             1,
             3,
             6,
             7
           ],
           "displayName": "daniel aof",
           "givenName": "daniel",
           "n": "",
           "profileCardParams": "uid=110773284060173603999&bc=0&hl=en&service=reader&name=daniel+aof&s=AB_q7XFHm_xEV2O42ni2MqSk6DR7XOLB1A",
           "groupId": [
             "18"
           ],
           "friendsFeedsCount": 1,
           "encodedSharersList": "CJzxtfScHhCvuuG7lAIQuc6YwvkDELTcu-fYBhCb5prkwAwQvty1wGU"
         }
       ]
     }
 
/friend/feeds
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Discover feeds from your follow

* Path::

    https://www.google.com/reader/api/0/friend/feeds

* Methods::

    GET

* request parameters:

    - output:  json
    - ck      1319794036488
    - client:  <application Name>


* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/friend/feeds?output=json&ck=<timeStamp>&client=<application Name>

* response::

     {
       "friendsFeeds": [
         {
           "friendUserId": "09113701262191614748",
           "feeds": [
             {
               "title": "Google Reader",
               "htmlUrl": "http://www.google.com/reader/shared/09113701262191614748",
               "streamId": "user/09113701262191614748/state/com.google/broadcast"
             },
             {
               "title": "Picasa Web Albums - 101204373271102322848",
               "htmlUrl": "http://picasaweb.google.com/101204373271102322848",
               "streamId": "feed/http://picasaweb.google.com/data/feed/base/user/101204373271102322848?alt=rss&kind=album&hl=en_US&access=public"
             },
             {
               "title": "&#25105;&#22312; Google &#38405;&#35835;&#22120;&#20013;&#30340;&#20849;&#20139;&#26465;&#30446;",
               "htmlUrl": "http://www.google.com/reader/shared/luckyqq527",
               "streamId": "user/09113701262191614748/state/com.google/broadcast"
             }
           ]
         }
       ]
     }
