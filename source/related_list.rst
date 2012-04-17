/related/list
--------------

GET some similar feeds with a feed.

* Methods::

    GET

* Authentication::

    Required.

* request parameters:

    - ck: <timestamp>
    - client:  <application Name>. 
    - n:       8
    - s:       <feed url>
    - output:  json

* Post Data::

    None

* example::

    https://www.google.com/reader/api/0/related/list?n=8&s=feed/http://www.codeproject.com/webservices/articlerss.aspx?cat=1&output=json&ck=<timeStamp>&client=<application Name>

* response::

        {
          "recs": [
            {
              "title": "MSDN: U.S. Local Highlights",
              "snippet": "The latest developer information for the United States.",
              "streamId": "feed/http://msdn.microsoft.com/rss.xml",
              "impressionTime": "-1"
            },
            {
              "title": "ScottGu's Blog",
              "snippet": "Scott Guthrie lives in Seattle and builds a few products for",
              "streamId": "feed/http://weblogs.asp.net/scottgu/rss.aspx",
              "impressionTime": "-1"
            },
            {
              "title": "CodeBetter.Com",
              "snippet": "Stuff you need to Code Better!",
              "streamId": "feed/http://codebetter.com/blogs/MainFeed.aspx",
              "impressionTime": "-1"
            },
            {
              "title": "Lambda the Ultimate - Programming Languages Weblog",
              "snippet": "Programming languages news, articles and discussion",
              "streamId": "feed/http://lambda-the-ultimate.org/rss.xml",
              "impressionTime": "-1"
            },
            {
              "title": "CodePlex Published Projects For Tag WPF",
              "snippet": "This feed lists the last 100 published projects available on",
              "streamId": "feed/http://www.codeplex.com/rss.ashx?behavior=bytag&tagName=WPF",
              "impressionTime": "-1"
            }
          ]
        }
        
        
 
