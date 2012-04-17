/conversation/edit
------------------
Close comments 

* Path::

    https://www.google.com/reader/api/0/conversation/edit

* Methods::

    POST

* request parameters:
    - client:  <application Name>


* Post Data:

    - s:     <StreamId_>
    - i:     tag:google.com,2005:reader/item/c460ace9a3485dca
    - action:        closecomments
    - c:     true
    - T: <token>


* example::

    https://www.google.com/reader/api/0/conversation/edit?client=<application Name>

* response::

    OK
 
