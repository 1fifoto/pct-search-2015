# pct-search-2015
Pacific Crest trail (PCT) Search and Map function

This repository contains the following related sub-projects
1. A simple Python script that returns the closest Pacific Crest Trail mile
marker to a supplied latitude and longitude coordinate.
2. A simple PHP web-site that takes a supplied latitude and longitude
coordinate and presents the closest Pacific Crest Trail mile marker.

pct-search.py
=============
The `pct-search.py` file is a simple python script that returns the closest
Pacific Crest Trail (PCT) mile marker waypoint for a supplied latitude and
longitude. It depends on the `doc.kml` file which is zipped within the
[halfmiles_pct_tracks_waypoints_2015.kmz](http://www.pctmap.net/google/) file.

To run, just supply a latitude and longitude coordinates (e.g. received from a
device like the SPOT Satellite Messenger) and you'll get back the mile marker
waypoint (note: half-mile markers are written in the format `0156-5`), the
latitude and longitude of the mile marker, and the distance between the
supplied coordinate and the mile marker as calculated by the haversine equation
(as the crow files).

A sample usage is:
```
./pct-search.py 33.59556,-116.57129
0156 33.59643,-116.57026 0.1mi
```

Typically the latitude and longitude coordinates, and the mile marker waypoint
values are then manually inserted into the Google docs Mileage Log spreadsheet.

Note: By internally uncommenting lines in pct-search.py, it can also generate
either `mile_markers` for `index.php` or `pctMileMarkers` for `script.js`
mentioned below.

pct-search/index.php
====================
Alternatively to the `pct-search.py` is the `pct-search/index.php` web-site
PHP file which provides a web interface to convert a latitude and longitude
(typically sent by a SPOT Satellite Messenger) to the nearest PCT mile. The
latitude and longitude coordinates, and the mile marker waypoint values are
then manually inserted into the Google docs Mileage Log spreadsheet.

