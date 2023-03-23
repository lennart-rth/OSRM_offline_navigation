# Fahrrad-Navi
Navigation with the osmr library to navigate along a preloaded track from komoot.

--Curently in developement--

The VisualStudiotest dir is a hello world only for testing the building and debuging with Visual Studio

Two ways to use OSMR:

1. Use the HTTP API with the OSMR Release Folder

Setup the HTTP Server:

osrm-extract -p Profiles/car.lua berlindata/data.osm.pbf
osrm-partition.exe berlindata/data.osrm
osrm-customize.exe berlindata/data.osrm
psrm-routed --algorithm ch  berlindata/data.osrm

OR alternativly by :
osrm-extract -p Profiles/car.lua berlindata/data.osm.pbf
osrm-contract berlindata/data.osrm
osrm-routed --algorithm ch berlindata/data.osrm

Api example Usage:
http://127.0.0.1:5000/route/v1/driving/13.388860,52.517037;13.385983,52.496891?steps=true


2. Use the LIB-OSMR as a C++ Library from the OSMR-backend Folder. (An Example of Usage is given under OSMR-backend/example/example.cpp nativs Tool)
Example folder is uploaded, but probably doesnt work without the other dirs.

To Build the example projekt the best way is using CL compiler:
Use the special "x64 Natives Tool Command Promt For VS 2019"-Console from Virtual Studi: (founf by typing name in the Search field of Task bar)
First navigate to the Folder where the exmaple.cpp is located.
Copy the following Command in the Promt and press enter:
cl /EHsc /MD -I C:\Users\Ahoi\Desktop\osrm-backend\include -I C:\Users\Ahoi\Desktop\osrm-backend\osrm-deps\include -I C:\Users\Ahoi\Desktop\osrm-backend\third_party\variant\include -I C:\Users\Ahoi\Desktop\osrm-backend\third_party\flatbuffers\include example.cpp C:\Users\Ahoi\Desktop\osrm-backend\build\Release\osrm.lib /link /LIBPATH:"C:\Users\Ahoi\Desktop\osrm-backend\osrm-deps\lib"

All cMake Files are not relevant since there is a mistake in cmake.txt and building by cMAke gives an Error.
