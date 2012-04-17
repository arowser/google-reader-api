Google Reader architecture introduce
===========================================

Google Reader is a feed aggregators tool for gathering, reading, and sharing all the interesting blogs and websites you read on the web. 
The three layers for feed aggregators:

Layer 1  The layer that parse feeds. It's not the easiest job. "But, it's just xml, it should be easy". It's not. It's just xml. It's just many differents and incompatible xml formats. You also perhaps need to understand all non standard feeds that mix some features from differents standards.
Layer 2  The database layer. Once you've parsed your feed, you need to store it in a database, and and interesting things like "items read", etc.
Layer 3  The user interface.
Google Reader offer in fact acces to layer 1 only, or layer 1+2 or layer 1+2+3.

You can have acces to layer 1 only. Feeds are parsed by Google Reader, and Google Reader give you access to a new Atom feed that contains same data as the original feed, but always with the same output format  Atom.

You can have acces to layer 1+2. This documents purpose is about how to acces to layer 1+2 from Google Reader in order to create your own layer 3.

Of course, you have access to layer 1+2+3 because it's Google Reader's main product.
 
