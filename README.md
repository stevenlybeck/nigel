nigel
=====

Open Street Map renderer in JavaScript, HTML and Canvas


This is a JavaScript-based stack intended to chew on OSM's XML data and render 
beautiful maps directly from a store of the data.

In order to reduce the load on the API service, you must run a local copy of Varnish like this:
	sudo varnishd -a 127.0.0.1:9191 -b www.overpass-api.de:80 -s file,/tmp,500M

Any other proxy or intermediary will also work.

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
- Idea:
-- Create a style language.
-- "drawing" a map involves compiling the style language and the map data into 
   canvas API calls
-- This should be easily applied to other drawing tech as well - SVG, etc...
- Maps are distorted at high latitudes
-- Test areas:
--- Longyearbyen, Norway
---- goToMap(78.2244787,15.6343946, 1)
---- goToMap(78.2244787,15.6343946, 5)
--- Puerto Williams, Chile
---- goToMap(-54.9332995,-67.616, 1)
---- goToMap(-54.9332995,-67.616, 5)
--- Quito, Ecuador
---- goToMap(-0.1865943,-78.4305382, 1)
---- goToMap(-0.1865943,-78.4305382, 5)
-- We need to use a real projection and scale the y-axis (lat) to match the x-axis (lon)
-- Zoom levels should correspond to a geographic distance or height-of-map-in-latitude
--- Since latitude and distance have a direct correspondance, the width-in-longitude can be determined based on the latitude position
- Label rotation seems off since updating the map projection code.
- Moving the map doesn't seem to work since updating the map projection code.


By: Steven Lybeck
Licensed under the MIT license: http://www.opensource.org/licenses/mit-license.php
