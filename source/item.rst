/item
--------
/item/edit
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* Path::

    http://www.google.com/reader/api/0/stream/items/edit

* Methods::

    GET  

* Authentication::

    Required.

* request parameters:

    - ck      1319597245680
    - client  link-bookmarklet-form

* Post Data:

    - title   AdWords Ads Writing Tips
    - url     http://www.drexplain.com/isv-kaizen-blog/adwords/adwords-ads-writing-tips/
    - srcUrl  http://www.drexplain.com/isv-kaizen-blog
    - srcTitle        ISV Kaizen
    - annotation      great
    - snippet  <html code>
    - share   true
    - linkify false
    - T       <token>


* example::

    https://www.google.com/reader/api/0/item/edit?ck=<timeStamp>&client=link-bookmarklet-form

* response::

    OK

/delete
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
delete item from your share items.

* Path::

    http://www.google.com/reader/api/0/item/delete

* Methods::

    POST

* request parameters:
    - client:  <application Name>
    - ck: <timestamp>

* Post Data:

    - i:     tag:google.com,2005:reader/item/fe7e4a577aa9ba78
    - T: <token>

* example::

    https://www.google.com/reader/api/0/item/delete?ck=<timeStamp>&client=<application Name>

* response::

    OK
 
/item/likers
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Path::

    https://www.google.com/reader/api/0/item/likers

* Methods::

    GET 

* request parameters:

    - i:     tag:google.com,2005:reader/item/232086a7a92de63a
    - output:  json
    - ck      1320030033628
    - client:  <application Name>

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/item/likers?i=tag:google.com,2005:reader/item/232086a7a92de63a&output=json&ck=<timeStamp>&client=<application Name>

* response::

        {
          "friends": [
            {
              "userIds": [
                "01868863025322816778"
              ],
              "profileIds": [
                "111348930475871926771"
              ],
              "contactId": "-1",
              "photoUrl": "/s2/photos/public/AIbEiAIAAABECPPzzde3hOC_nQEiC3ZjYXJkX3Bob3RvKig5NzE2M2E2MjEzY2E1NTViZDVmOWY5OTlkYWM3MjdjNDdjODljZTFlMAGyDjMQOcwQRDBfwU0nzECbUClvhg",
              "location": "Nanjing，China",
              "stream": "user/01868863025322816778/state/com.google/broadcast",
              "flags": 32,
              "types": [
                6
              ],
              "displayName": "robby lee",
              "givenName": "robby",
              "n": "",
              "profileCardParams": "uid=111348930475871926771&bc=0&hl=en&service=reader&name=robby+lee&clt=Follow+robby+lee&clue=amF2YXNjcmlwdDp0b3AuRlJfRnJpZW5kc19zdGFydEZvbGxvd2luZygnMDE4Njg4NjMwMjUzMjI4MTY3NzgnLCAnMTExMzQ4OTMwNDc1ODcxOTI2NzcxJywgJ3JvYmJ5IGxlZScp&s=AB_q7XHYO7CkKITIsQs7xA3d4WAl0yLgkA",
              "occupation": "Student"
            }
          ]
        }
        
 
