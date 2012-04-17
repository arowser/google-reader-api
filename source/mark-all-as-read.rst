/mark-all-as-read
--------------------

* Methods::

    POST

* Path::

    https://www.google.com/reader/api/0/mark-all-as-read

* request parameters:
    - client:  <application Name>

* Post Data:

    - s:       user/<usrId_>/state/com.google/followers
    - T: <token>

* example::

    https://www.google.com/reader/api/0/mark-all-as-read?client=<application Name>

* response::

     OK
 
