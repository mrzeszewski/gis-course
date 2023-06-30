# GIS course
Here you will find data and description of exercises that we will be doing during our online and onsite meetings. Course will be updated as we will go further according to what we will be able to do. Course will be separated into thematic parts that not neccessarily correspond to separate meetings (we can go through two meetings in on or the other way around).

***A note:** most kinds of spatial and location based analysis can be treated as a puzzle with a more than one solution. It is often the case that our workflow, accuracy and precision of the analysis is determined by the quality of the data and its nature but it is also influenced by our skillset and even worldview. You do not need to know the fastest or best solution. In most cases you need an approximation that is good enough. Do not be afraid to experiment and choose freely from a wide array of tools and plugins at your disposal. **Have fun with GIS!***

## Part 1 – Simple location analysis with buffers, object selection, counting points and real-world distances
What we will learn:
1. Getting data from Open Street Map (OSM) – using QuickOSM plugin in QGIS (_you should already know how to do it_).
2. Checking the data and cliping it to the area of interest (_Vector/Geoprocessing tools/Clip_)
3. Deleting attributes thar are not necessary or empty (_Attribute table - Delete Fields_)
4. Using geopackage for storing data (_Sidenote – layers in the Data folder are in a legacy format called ESRI Shapefile for the purpose of compatibility only_). 
5. Visualizing data – using different basemaps (_HCMGIS plugin_)
6. Storing basemaps and whole maps as raster files with georeferences for future use (_Save as image with world fil_e)
7. Transforming real world questions into GIS abstracts (_an introduction to spatial analysis and the way we think about spatial problems_)
8. Creating distance based buffers (_Vector/Geoprocessing tools/Buffer_)
9. Using buffer polygons to find points and object that fulfill various criteria with two different tools (_1. Vector/Research Tool/Select by location; 2.Count points in polygon_)
10. Create isochrones (_Catchments_) to approximate real-world distances (_Location Lab plugin_). You will need a free [OpenRouteService account](https://openrouteservice.org/)
11. Bonus – create an interactive web map (_qgis2web plugin_)

**```Task 1: Group exercise. Create a map showing fire emergency readiness of Kiel kindergartens using locations of fire  hydrants and fire stations. Assume that an object is close enough to fire hydrant if it is within 100 meters and close enough to fire station when it is within 5 minutes travel distance.```**

## Part 2 – Using remote data sources: WMS and WFS.
What we will learn:
1. Searching for remote data services and reading _GetCapabities_ outputs.
2. Attaching remote WMS and WFS services to QGIS data sources.
3. Using WMS as a basemap and using GetFeatureInfo function.
4. Using WFS to download and save data.

## Part 3 – Exploring location factors: estimating service area and population influence using geoprocessing tools. 
What we will learn:
1. Making visual analysis on objects (kindergartens) spatial density in districts (_Vector/Analysis Tools/Count points in polygons_)
2. Creating new attributes basing on existing values (_number of residents per one feature(kindergarten) using Field Calculator in Attribute Table_) 
3. Calculating attribute values using object properties and geometries (_calculate area of the feature and population density using Field Calculator_)
4. Creating service areas using Voronoi polygons (_Vector/Geometry Tools/Voronoi polygons_)
5. Estimating population for service areas (Voronoi polygons) from district data. 
   - Cuting districts overlayed by each Voronoi polygon: _Vector/Geoprocessing tools/Intersect_
   - *Sidenote-when saving result of the intersect algorithm into Geopackage it is something necessary to delet FID column in the attribute table.
   - It is neccessary to transfer population density and area from each district to each Voronoi polygon - we can do it by basing new values on how much of the district area is within each Voronoi. But we cannot do it through geometry predicates (Intersect/Within/Contains...etc) as they share borders. Instead we can transform polygons into points. Be aware that _Centroids_ are not enough as they can be positioned outside the shape (give it a try!). Instead we can use _Pole of Inaccesibility_ to give us a nice set of points.
   - But **before** we calculate those points we need to have the population for those new polygons - calculate new area and then new population using population density. 
   - Having points with data we can calculate this new values for Voronoi polygons we can use algorithm Join attributes by location(summary) to sum values of population from points and add it to polygons
6. We now see which kindergarten serves the largest number of people.

**```Task 2 (final): Group exercise. Create a map showing the best locations for new parcel lockers. Start by locating existing ones from OSM(amenity:parcel_locker). Think what factors shold be included? What results do you want? Your solution need to take into account at least two spatial criteria```**



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
