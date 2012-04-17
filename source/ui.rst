/ui
===========================================
Some image and css url like:

 https://www.google.com/reader/ui/441323228-corner_bl.gif

/link-frame
===========================================
Show some frame like send mail, share with note....

 https://www.google.com/reader/link-frame

/permalink
===========================================
Some  permalink page like 404 error.

 https://www.google.com/reader/permalink/item/tag:google.com,2005:reader/item/c460ace9a3485dca

/js-load-error
===========================================
https://www.google.com/reader/js-load-error?src=<application Name>&u=<usrId_>&type=bad-json&msg=/reader/api/0/tag/list?output=json  (SyntaxError: syntax error)&ck=<timeStamp>

/email-this
===========================================
Send item to mail address. 

* URL::

   http://www.google.com/reader/email-this?ck=<timeStamp>lient=<application Name>

* Methods::

     POST

* Authentication::

   Required.

*   POST DATA:

   - i:       The item identifier. See the previous section for details.
   - emailTo: The email addresses to send the item to. You can send to multiple recipients. These addresses are in the format , ,
   - comment: The email body
   - subject: The email subject
   - ccMe:    Whether to send the email to your own GMail account also. Can be true or false.
   - T: <token>

* example::

    Here’s some example   POST data to send an email.
    i=i=tag:google.com,2005:reader/item/0816b6dbac1d768&emailTo= <example@example.com>, &comment=Check this out&subject=Google Reader API&ccMe=false&T=abcde.ABCD1234abc

* response::

    OK

/overview
===========================================
https://www.google.com/reader/overview?ck=<timeStamp>&client= scroll
https://www.google.com/reader/view/?authuser=1
 
