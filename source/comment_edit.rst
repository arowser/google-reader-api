/comment/edit
-----------------

* Path::

    https://www.google.com/reader/api/0/comment/edit

* Methods::

    POST

* request parameters:
    - client:  <application Name>

* Post Data:

    - s:     <StreamId_>
    - i:     tag:google.com,2005:reader/item/c460ace9a3485dca
    - action        addcomment
    - output        json
    - comment:       test
    - T: <token>

* example::

    https://www.google.com/reader/api/0/comment/edit?client=<application Name>

* response::

    OK
 
