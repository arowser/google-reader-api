/people
--------
/search
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Search google reader People 

* Path::

    https://www.google.com/reader/api/0/people/search

* Methods::

    GET

* request parameters:
    - q:       <keyword>
    - output:  json
    - ck      1319794036488
    - client:  <application Name>


* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/people/search?q=daniel&output=json&ck=<timeStamp>&client=<application Name>

* response::

       {
         "friends": [
           {
             "userIds": [
               "15262232593538433084"
             ],
             "profileIds": [
               "115699426100289857429"
             ],
             "contactId": "-1",
             "photoUrl": "/s2/photos/public/AIbEiAIAAABECJXPl-q-m-Tv2QEiC3ZjYXJkX3Bob3RvKig5N2MyNWZmNDkxZjU0ODQyZDQwNWViY2JiYTFmYmIwNWEwOGIxODJjMAE0Cm6GBd53tbFxMx3E94HGJ3lwXA",
             "location": "Mountain View, CA",
             "stream": "user/15262232593538433084/state/com.google/broadcast",
             "flags": 32,
             "types": [
               6
             ],
             "displayName": "Daniel Dulitz",
             "givenName": "Daniel",
             "n": "",
             "profileCardParams": "uid=115699426100289857429&bc=0&hl=en&service=reader&name=Daniel+Dulitz&clt=Follow+Daniel+Dulitz&clue=amF2YXNjcmlwdDp0b3AuRlJfRnJpZW5kc19zdGFydEZvbGxvd2luZygnMTUyNjIyMzI1OTM1Mzg0MzMwODQnLCAnMTE1Njk5NDI2MTAwMjg5ODU3NDI5JywgJ0RhbmllbCBEdWxpdHonKQ&s=AB_q7XH2KSWP7R5HfTYyPnJvndFFIZ5G6g",
             "occupation": "Product Manager",
             "websites": [
               {
                 "title": "Facebook",
                 "url": "http://www.facebook.com/people/Daniel-Dulitz/536927371"
               },
               {
                 "title": "Google Reader",
                 "url": "http://www.google.com/reader/shared/15262232593538433084"
               },
               {
                 "title": "FriendFeed",
                 "url": "http://friendfeed.com/polymath"
               },
               {
                 "title": "http://www.linkedin.com/pub/0/15/409",
                 "url": "http://www.linkedin.com/pub/0/15/409"
               },
               {
                 "title": "Twitter",
                 "url": "http://twitter.com/dulitz"
               },
               {
                 "title": "Picasa Web Albums",
                 "url": "http://picasaweb.google.com/dulitz"
               }
             ]
           }
         ],
         "friendsFeedsCount": 0
       }
 
/profile
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET profile of user

* Path::

    https://www.google.com/reader/api/0/people/profile

* Methods::

    GET

* request parameters:
    - output:  json

* example::

    http://www.google.com/reader/api/0/people/profile?u=14290265284323789574&output=json

* response:

    Same ouput with `/search`_
 
/profile
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET profile of user

* Path::

    https://www.google.com/reader/api/0/people/profile

* Methods::

    GET

* request parameters:
    - output:  json

* example::

    http://www.google.com/reader/api/0/people/profile?u=14290265284323789574&output=json

* response:

    Same ouput with `/search`_
 
