# OSRM offline navigation
A implementation of the osrm routing engine for  a shortest path in a road network.

A shortes path is found by a local engine running osrm on a raspberry pi.
The found path is then converted into a gpx file and proccesed into a set of instructions. (e.g. "Turn left onto ABC Street").

All this can be done offline as long as the mapt tile (routing) data is stored localy.
