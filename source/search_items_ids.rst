/search/items/ids
---------------------------
Search and get items id by keyword from google reader.

* Methods::

    GET

* Authentication::

    Required.

* request parameters:

    - client:  <application Name>. 
    - q       <keyword>
    - num:    1000
    - output: json
    - s:  <streamId_>

* example::

    https://www.google.com/reader/api/0/search/items/ids?q=isv&num=10&output=json

* response::

    {
      "results": [
        {
          "id": "3172710423366646353"
        },
        {
          "id": "-6837987485876846087"
        },
        {
          "id": "8011195446291294775"
        },
        {
          "id": "573440608357140489"
        },
        {
          "id": "-108567601429759368"
        },
        {
          "id": "6332718904656144476"
        },
        {
          "id": "3525187997534391124"
        },
        {
          "id": "2328952297057408783"
        },
        {
          "id": "3698196767931245998"
        },
        {
          "id": "8671524315603609522"
        },
        {
          "id": "-3598003114819973846"
        },
        {
          "id": "3511032366751727750"
        }
      ]
    }
 
