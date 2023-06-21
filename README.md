# GIS course
Here you will find data and description of exercises that we will be doing during our online and onsite meetings. Course will be updated as we will go further according to what we will be able to do. Course will be separated into thematic parts that not neccessarily correspond to separate meetings (we can go through two meetings in on or the other way around).

***A note:** most kinds of spatial and location based analysis can be treated as a puzzle with a more than one solution. It is often the case that our workflow, accuracy and precision of the analysis is determined by the quality of the data and its nature but it is also influenced by our skillset and even worldview. You do not need to know the fastest or best solution. In most cases you need an approximation that is good enough. Do not be afraid to experiment and choose freely from a wide array of tools and plugins at your disposal. **Have fun with GIS!***

## Part 1 – Simple location analysis with buffers, object selection, counting points and real-world distances
What we will learn:
1. Getting data from Open Street Map (OSM) – using QuickOSM plugin in QGIS (_you should already know how to do it_).
2. Checking the data and cliping it to the area of interest (_Vector/Geoprocessing tools/Clip_)
3. Using geopackage for storing data (_Sidenote – layers in the Data folder are in a legacy format called ESRI Shapefile for the purpose of compatibility only_). 
4. Visualizing data – using different basemaps (_HCMGIS plugin_)
5. Storing basemaps and whole maps as raster files with georeferences for future use (_Save as image with world fil_e)
6. Transforming real world questions into GIS abstracts (_an introduction to spatial analysis and the way we think about spatial problems_)
7. Creating distance based buffers (_Vector/Geoprocessing tools/Buffer_)
8. Using buffer polygons to find points and object that fulfill various criteria with two different tools (_1. Vector/Research Tool/Select by location; 2.Count points in polygon_)
9. Create isochrones (_Catchments_) to approximate real-world distances (_Location Lab plugin_)
10. Bonus – create an interactive web map (_qgis2web plugin_)

**```Task 1: Group exercise. Create a map showing fire emergency readiness of Kiel kindergartens using locations of fire  hydrants and fire stations. Assume that an object is close enough to fire hydrant if it is within 100 meters and close enough to fire station when it is within 5 minutes travel distance.```**

## Part 2 – Using remote data sources: WMS and WFS.
What we will learn:
1. Searching for remote data services and reading _GetCapabities_ outputs.
2. Attaching remote WMS and WFS services to QGIS data sources.
3. Using WMS as a basemap and using GetFeatureInfo function.
4. Using WFS to download and save data.

## Part 3 – Using remote data sources: WMS and WFS.
What we will learn:


## Useful links and resources

* [AdV MetadatenInformationsSystem](https://advmis.geodatenzentrum.de/startseite) - a place when you can search for spatial data for Germany. This is a metadata information system (MIS) of the working group of the surveying authorities of the federal states of the Federal Republic of Germany (AdV). It enables an overview and research into the digital geodata and geodata services of the AdV member administrations.
* [Schleswig-Holstein Geoportal](https://www.gdi-sh.de/gdish/DE/Geoportal/geoportal_node.html)
* [Kiel Open Data](https://www.kiel.de/de/kiel_zukunft/statistik_kieler_zahlen/open_data/index.php)
* WFS:
  * [INSPIRE WFS SH management units ALKIS](https://advmis.geodatenzentrum.de/trefferanzeige?docuuid=8626da70-c59c-4139-abbe-0b638f9713ad)
  * [INSPIRE WFS SH parcels/land ALKIS](https://advmis.geodatenzentrum.de/trefferanzeige?docuuid=defbc2f3-52f0-4b0e-a196-908d678086b3)
* WMS:
  * [INSPIRE WMS SH building – 2D ALKIS (display service)](https://advmis.geodatenzentrum.de/trefferanzeige?docuuid=775c9ae4-13e4-49a2-a86b-97bb9b3d4b5a)
  * [WMS_SH_DOP20col_OpenGBD - Orthophoto maps](https://advmis.geodatenzentrum.de/trefferanzeige?docuuid=2e38287e-5ccc-4562-a279-ae45060a5585)
  * [WMS_SH_ALKIS_OpenGBD](https://advmis.geodatenzentrum.de/trefferanzeige?docuuid=560b0d3d-008a-4ded-ae7b-97880c7eefd8)
