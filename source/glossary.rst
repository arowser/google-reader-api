Glossary
===========================================

.. _request-label:

*request parameters Description*:
--------------------------------------

+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|Parameter|   Value       |  Description                                                                                                                                     |
+=========+===============+==================================================================================================================================================+
|n        | count         |  Number of items returns in a set of items (default 20, up to a maximum of 10,000)                                                               |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|client   | client        | A string that identify the client used. I suppose it's for logging/stat purpose, or perhaps to make some adjustement for some clients,           |
|         |               | Old GoogleReader interface use 'lens', new one use 'scroll', iphone verison is 'mobilescroll'.                                                   |
|         |               | Google probably uses this field to gather data on who is accessing the API, so I’d advise using your own unique string to identify your software |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|r        |  order        |  n [a|d|n|o|c]  Sort order of item results. d or n gives items in descending date order, o in ascending order.                                   |
|         |               |  a: "magic", c: items with most recent commens first                                                                                             |
|         |               |  By default, items starts now, and go back time. (default value is d)                                                                            |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|ot       | start_time    |  The time (unix time, number of seconds from January 1st, 1970 00:00 UTC) from which to start to get items.                                      |
|         |               |  Only works for order r=o mode. If the time is older than one month ago, one month ago will be used instead.                                     |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|nt       | end_time      |  The time (unix time, number of seconds from January 1st, 1970 00:00 UTC) from which to end to get items.                                        |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|ck       | timestamp     |  current time stamp, probably used as a quick hack to be sure that cache won't be triggered.                                                     |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|xt       | exclude_target|  Another set of items suffix, used to exclude certain items from the feed. you can query all items from a feed that are not flagged as read.     |
|         |               |  This value start with feed/ or user/, not with !http:// or www. For example, using xt=user/-/state/com.google/read will exclude items that the  |
|         |               |  current user has marked as read, or xt=feed/[feedurl] will exclude items from a particular feed (obviously not useful in this request, but xt   | 
|         |               |  appears in other listing requests)                                                                                                              |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|c        | continuation  | a string used for continuation process. Each feed return not all items, but only a certain number of items.                                      |
|         |               | You'll find in the atom feed (under the name gr:continuation) a string called continuation. Just add that string as argument for this parameter, |
|         |               | and you'll retrieve next items.                                                                                                                  |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|source   | source        | RECOMMENDATION: subscribe from recommandation                                                                                                    |
|         |               | SUBSCRIBE_BUTTON: when you click Subscribe butthon                                                                                               |
|         |               |                                                                                                                                                  |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|s        | streamId      | RECOMMENDATION: subscribe from recommandation                                                                                                    |
|         |               | SUBSCRIBE_BUTTON: when you click Subscribe butthon                                                                                               |
|         |               | user/03125399518623059338/state/com.google/broadcast                                                                                             |
|         |               | /pop/topic/top/language/en                                                                                                                       |
|         |               | user/-/state/com.google/reading-list                                                                                                             |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|output   | output        |  The format of the returned output. may be 'json' or 'xml'                                                                                       |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|merge    | false         | If true, the response will be combined into a single set of items before ranking and n limit application.                                        |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|sharers  | CKfbjpeeFxgB  | Encoded list of possible sharers, for whom comments will be fetched. Obtained from ApiFriendList.                                                |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|likes    | false         | Whether or not to fetch likes                                                                                                                    |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|comments | false         | Whether or not to fetch comments                                                                                                                 |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|mediaRss | false         | Whether or not to include MediaRSS elements from the original feed in the response                                                               |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|hl       | en            | Language to use for the response. If not specified, will be inferred based onAccept-Language HTTP header, IP, user preferences, etc              |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|at       |               |  identify mult user                                                                                                                              |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|start    |               |  start index                                                                                                                                     |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|num      |               |  result number                                                                                                                                   |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

Note::
  continuation has no meaning, it's just a string to help you find next items. You should not rely on its value to do anything else than that (even if this document will explain how that continuation is generated).
 

.. _post-label:

*POST parameters Description*:
--------------------------------------

+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|Parameter|   Value       |  Description                                                                                                                                     |
+=========+===============+==================================================================================================================================================+
|a        |               |  A new tag to add. This can take one of several                                                                                                  |
|         |               |  formats depending on the type of tag you’re                                                                                                     |
|         |               |  adding to the item. See the notes at the bottom                                                                                                 |
|         |               |  of this table for details.                                                                                                                      |
|         |   <tagId>     |  example:                                                                                                                                        |
|         |               |  user/<usrId_>/state/com.google/starred                                                                                                          |
|         |               |  user/<usrId_>/state/com.google/like                                                                                                             |
|         |               |  user/<usrId_>/state/com.google/broadcast                                                                                                        |
|         |               |  user/<usrId_>/label/<tag Name>                                                                                                                  |
|         |               |  user/<usrId_>/state/com.google/read                                                                                                             |
|         |               |  user/<usrId_>/state/com.google/kept-unread                                                                                                      |
|         |               |  user/<usrId_>/state/com.google/dislike                                                                                                          |
|         |               |                                                                                                                                                  |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|r        |               |  Remove an existing tag. This tag can take one of                                                                                                |
|         |               |  several formats depending on the type of tag you’re                                                                                             |
|         |               |  removing from the item. See the notes at the bottom of                                                                                          |
|         |               |  this table for details.                                                                                                                         |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|async    |               | Can be either true or false. This appears to be a utility argument for Google’s own website,                                                     |
|         |               | as it doesn’t seem to make a difference to my API calls.                                                                                         |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|s        |               | The feed that this item belongs to. See the previous section for information on the format of this argument.                                     |
|         |               |    feed/http://www.codeproject.com/webservices/articlerss.aspx?cat=1                                                                             |
|         |               |     user/<usrId_>/state/com.google/alerts/15759546710344019162                                                                                   |
|         |               |     user/<usrId_>/label/<old label name>                                                                                                         |
|         |               |     user/<usrId_>/source/com.google/bundle-item                                                                                                  |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|streams  |               | same with s                                                                                                                                      |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|i        |               | The item you want to tag. This is in the format tag:google.com,2005:reader/item/[item identifier].                                               |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|T        |               | 1.As usual this is your token.                                                                                                                   |
|         |               | 2. Titles                                                                                                                                        |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|it       |               | timestampUsec                                                                                                                                    |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|trans    |  true         |  only use when need trans to my language                                                                                                         |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|bundle   |               | user/<usrId_>/bundle/<bundleName>                                                                                                                |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|action   |               |  hidefollowing   addcomment closecomments                                                                                                        |
|         |               |  removefollowing                                                                                                                                 |
|         |               |  addfollowing                                                                                                                                    |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|output   | json          |  The format of the returned output. may be 'json' or 'xml'                                                                                       |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|full     | true          |  if vlue is false some info will not return like "crawlTimeMsec",will not include full content.                                                  |
+---------+---------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

Note::

   some parameters only available for special request not be description in here 
   some parameters is meaning clear not be here too, like "url", "title",'comment' 

*Response Description*
--------------------------------------

+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|Parameter       |  Description                                                                                                                                     |
+================+==================================================================================================================================================+
|id              | StreamId_                                                                                                                                        |
|id              | ItemId_ for the item (signed base 10 version).                                                                                                   |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|title           | title   string                                                                                                                                   |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|c               |  continuation                                                                                                                                    |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|self            |  an array of objects which contain a google link to this list                                                                                    |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|alternate       |  an array of objects which contain non-Google links to the feed (usually the author's RSS)                                                       |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|updated         |  Updated timestamp                                                                                                                               |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|items           |  an array of item objects                                                                                                                        |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|crawlTimeMsec   | when the item was crawled by Google Reader                                                                                                       |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
| timestampUsec  | time in microseconds since the epoch that the item appeared in the direct stream that it was in.                                                 |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|categories      | an array of categories to which this item belongs. These appear to be user-specific                                                              |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|enclosure       | an array of enclosure objects. These are used mostly for podcasts/videocasts, they contain media items enclosed in the feed item.                |
|                | Enclosure items are composed of                                                                                                                  |
|                +----------+---------------------------------------------------------------------------------------------------------------------------------------+
|                |  href    |  A link to the media file                                                                                                             |
|                +----------+---------------------------------------------------------------------------------------------------------------------------------------+
|                |  type    |  An internet media type                                                                                                               |
|                +----------+---------------------------------------------------------------------------------------------------------------------------------------+
|                |  length  |  Length, in bytes                                                                                                                     |
+----------------+----------+---------------------------------------------------------------------------------------------------------------------------------------+
|type            |  An internet media type                                                                                                                          |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|mediaGroup      | appears to be an object storing an array of direct links to the enclosure media                                                                  |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|summary         | an object containing a description of the feed item                                                                                              |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|direction       | ltr or rtl                                                                                                                                       |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|contents        | contents string                                                                                                                                  |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|author          | Author string                                                                                                                                    |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|likeUsers       | An array of users who "like" the item                                                                                                            |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|comments        | An array of comments on the item                                                                                                                 |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|annotations     | An array of annotations on the item                                                                                                              |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|origin          | An origin object which stores                                                                                                                    |
+----------------+----------+---------------------------------------------------------------------------------------------------------------------------------------+
|                | streamId |  this is the feed/[feedurl] that Google uses to identify the feed                                                                     |
|                +----------+---------------------------------------------------------------------------------------------------------------------------------------+
|                | title    |  The feed title string                                                                                                                |
|                +----------+---------------------------------------------------------------------------------------------------------------------------------------+
|                | htmlUrl  |  The HTML url to the feed's homepage                                                                                                  |
+----------------+----------+---------------------------------------------------------------------------------------------------------------------------------------+
|directStreamIds |  array of StreamIds representing the direct streams that this item came from.                                                                    |
+----------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------+

StreamId 
----------

Description of stream IDs exposed by the Google Reader API.
"Streams" refer to collections of items in the Google Reader API. This includes feeds, items with a specific tag, or folders. Stream IDs are are string-based identifiers used to identify streams and are passed to many API methods.

Feed IDs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The url to query a specific feed. It's Google Reader way to access to layer 1 only. Note  This service is not related to an account and can be access without registration.
Streams that correspond to data that come from crawled feeds are of the form feed/<feed URL>, for example:

feed/http://googleblog.blogspot.com/atom.xml
feed/http://blogsearch.google.com/blogsearch_feeds?q=mihai parparita&hl=en&scoring=d&num=10&output=atom

Tag IDs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Tags can be applied to items via the edit tag method and to subscriptions via the edit subscription method. Once a tag is applied, the tag is available as a stream, with the tag itself becoming the stream ID.

Tag stream IDs are of the form user/<user ID>/<tail>. <user ID> is the user's identifier, normally a numeric value obtained from the user info method, but "-" may also be used for authenticated requests to signify the ID of the authenticated user.

<tail> is different depending on the kind of tag being used:

System tag 
'''''''''''''''''''''''''''''''''''''''''''
System tags have a tail of the form state/com.google/<state>. Here are common item-level tags:

Here are common subscription-level tags:

=======================  ==========================================================================================================================================
State name               State meaning
=======================  ==========================================================================================================================================
like                     applied to liked items
read                     A read item will have the state read
kept-unread              Once you've clicked on "keep unread", an item will have the state kept-unread
link                     share-with-note (and the Note in Reader bookmarklet) will generate copies of items.
                         The copied items have a user/-/state/com.google/link origin stream
post                     There is also the concept of "notes" in Reader, which are standalone items that originate purely within Reader
created                  all notes that the user has created.
fresh                    When a new item of one of your feeds arrive, it's labeled as fresh. When (need to find what remove fresh label), the fresh label disappear.
starred                  When your mark an item with a star, you set it's starred state
broadcast                When your mark an item as being public, you set it's broadcast state
broadcast-friends        applied to the shared items of the users that are being followed, subscriptions, corresponds to the "People you follow" view in the UI
reading-list             All you items are flagged with the reading-list state. To see all your items, just ask for items in the state reading-list
tracking-body-link-used  Set if you ever clicked on a link in the description of the item.
tracking-emailed         Set if you ever emailed the item to someone.
tracking-item-link-used  Set if you ever clicked on a link in the description of the item.
tracking-kept-unread     Set if you ever mark your read item as unread.
=======================  ==========================================================================================================================================

Label
'''''''''''''''''''''''''''''''''''''''''''
User-created tags are added to items via the "Add tags" or "Edit tags" UI. They are of the form user/-/label/<name>, for example:

user/-/label/Foo
user/-/label/Foo Bar
Any character may be used as the name with the exception of: " ^ < > ? & \ /,.

Folder
'''''''''''''''''''''''''''''''''''''''''''
Folder stream IDs are the same as user-created tag stream IDs (i.e. they are in the same namespace).

Recommend stream IDs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
pop/topic/top/language/en

google alert Ids
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
user/<usrId_>/state/com.google/alerts/15759546710344019162

bundle Ids
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
user/11801782071179513560/bundle/Mark Bittman

Use in URLs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
When used as query parameters, stream IDs should be escaped as usual. More subtly, when used in paths (e.g. for the stream contents method) the stream ID should be escaped too.

example::

  http://www.google.com/reader/api/0/stream/contents/feed/http://www.example.com/search?q=foo

ItemId
----------

Items in Reader are referenced by globally unique item IDs. IDs are generally derived from the <id> attribute in Atom feeds and the <guid> attribute in RSS feeds. In the absence of those, the item URL may be used to generat the ID. In cases where the feed does not provide IDs or URLs (or they are not deemed "trustworthy", e.g. if more than one item in the feed response has the same ID or URL), then the ID will be computed from a signature of certain feed item properties (title, body, etc.).

Internally, item IDs are 64-bit numbers, and can be represented in API inputs and outputs in two forms:

Long form: The prefix tag:google.com,2005:reader/item/ followed by the ID as an unsigned base 16 number that is 0-padded so that it's always 16 characters wide.

Short form: The ID as a signed base 10 number.

Here's some sample mappings between the two forms:

=================================================== ======================== ==================================================================================
Long form                                               Short form                   notes
=================================================== ======================== ==================================================================================
tag:google.com,2005:reader/item/5d0cfa30041d4348       6705009029382226760     
tag:google.com,2005:reader/item/024025978b5e50d2       162170919393841362        Long form needs 0-padding
tag:google.com,2005:reader/item/fb115bd6d34a8e9f       -355401917359550817       Short form ends up being negative
=================================================== ======================== ==================================================================================

All API methods that take item IDs accept either form, but different outputs will contain different forms (for historical reasons).

If at all possible, you should not attempt to do conversions between forms. Store IDs from responses as string blobs, and pass them back as is to other API methods.
 
item/entry
-----------------
Sometimes called item, sometimes called entry, the item is the base element of a feed. An item usally contain a text, a title and a link, but can contain other properties. An RSS/Atom aggregator aggregates items. (Note: item is the RSS term, while entry is the Atom term).

usrId
-----------------
A 20 digits string used by google reader to identify a user. You don't really need to know it. You can always do things a way that user ID is not needed. Usually, when you need that information, just replace it by '-' and the user ID for current logged user will be used. The user ID never change for a user.

label
-----------------
This is the suffix to access to all items with a specific label
 
