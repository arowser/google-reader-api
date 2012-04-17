/rename-tag
------------
Rename tag name

* Methods::

    POST 

* Authentication::

    Required.

* request parameters:

    - client:                    <application Name>. 

* Post Data:

    - s:     user/<usrId_>/label/<old tag name>
    - t:     <old tagname>
    - dest:  user/<usrId_>/label/<new tag name>
    - T:     //s3wAqZ_mEpOvpF8hGNO8Pw

* example::

    https://www.google.com/reader/api/0/rename-tag?client=<application Name>

* response::

    OK
 
