/atom
===========================================
this section is about urls starting by http://www.google.com/reader/atom/
If you need to query a set of items in an atom format, just query http://www.google.com/reader/atom/ followed by the set of items suffix.

http://www.google.com/reader/atom/<StreamId_>

Each atom set contains by default 20 items. You can change that, and other behaviour by adding parameters to the query.

You can get from parameters table: request-label_

Exemple::

  http://www.google.com/reader/atom/feed/http://xkcd.com/rss.xml?n=17&ck=<timeStamp>=user/-/state/com.google/read
  All the 17 first items items from xkcd.com main feed that are not read can be found on the url
 
