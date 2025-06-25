
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

**```Task 2 (final): Group exercise. Create a map showing the best locations for new parcel lockers. Start by locating existing ones from OSM(amenity:parcel_locker). Think what factors shold be included? What results do you want? Your solution need to take into account at least two spatial criteria. UPDATE: PLEASE ALSO CREATE A SHORT STEP BY STEP DESCRIPTION OF WHAT YOU HAVE DONE```**
