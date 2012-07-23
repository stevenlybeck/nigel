nigel
=====

Open Street Map renderer in JavaScript, HTML and Canvas


This is a JavaScript-based stack intended to chew on OSM's XML data and render 
beautiful maps directly from a store of the data.


The initial code commit can process an XML file and render all the ways that 
sees in the XML file. If ways are named, it draws the name at the upper-left 
of a bounding box for the data we currently have for that way.

On the roadmap:
- More-efficient data retrieval. Is there a JavaScript-based geo database?
- Intermediate data stage for a given view before we begin to draw.
- Aspect-oriented rendering styles.
- Priority added by style. (As a rendering filter?)
- Modular rendering so custom code can be loaded by styles.
- Offline storage


By: Steven Lybeck
Licensed under the MIT license: http://www.opensource.org/licenses/mit-license.php
