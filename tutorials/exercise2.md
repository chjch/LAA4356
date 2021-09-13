# Test Drive on Overlay Analysis: Exercise 2

In this exercise, we will see how we can model suitability for industrial
areas.
The procedure shown below is meant to be an example and not considered as a
"_standard_" to follow.

## Criteria

1. Soil - Certain characteristics, such as high acidity, of soil are not
   suitable for sustaining structures.
   - Data: `Soils.shp`
   - Field: `corsteel` (susceptibility of uncoated steel to corrosion when in
     contact with the soil).
   - Geoprocessing: `Polygon to Raster`.
   - Criterion: `corsteel = 'Low'`
2. Flood risk - High flood risk raises serious safety concerns to industrial
   production.
   - Data: `Fema Flood Zones.shp`
   - Field: `RISK_LEVEL`
   - Geoprocessing: `Polygon to Raster`
   - criterion: `RISK_LEVEL = 'MODERATE TO LOW RISK AREAS'`
3. Accessibility - Proximity to major roads provides good accessibility which
   benefits the transportation of raw materials and manufactured products.
   - Data: `Roads.shp`
   - Field: n/a
   - Geoprocessing: `Buffer`
   - Criterion: within a half mile buffer of major roads.

## Assignment

In the word document created for exercise 1, please answer the following
questions:

1. How many 5m grid cells meet at least two of the three criteria?
2. What does meeting criteria 2 and 3 tell you about the grid cell?
3. How many hectares meet all the criteria? (i.e. calculate hectares based on
   grid cell count)