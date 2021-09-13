# Test Drive on Overlay Analysis: Exercise 1

## Description

Recall the _taxlot.shp_ introduced in
[Tutorial 1](1-software_and_data.md#property).
The _shapefile_ dataset contains three fields in its attribute table:

- _ACTYBLT_ (actual year built),
- _JV_ (just or market value of the parcel), and
- _DORUC_ (land use code).

Create three raster datasets with the following criteria.

1. `'ACTYRBLT' < 1990` (indicating at least a 60-year building by 2050)
2. `'JV'/acre < 300000` (30<sup>th</sup> percentile of parcel value)
3. `'DORUC' >= '001' AND 'DORUC' <= '009'` (current land use -- residential)

By combining these three criteria we find redevelopment opportunities for
residential areas.

## Assignment

Open a new word document, type your name, the class title, and the date in the
upper right corner.
Then, please answer the following questions:

1. How many 5m grid cells meet criteria 1 and 2, but not 3?
2. What does meeting criteria 1 and 2 tell you about the grid cell?
3. How many hectares meet all the criteria? (i.e. calculate hectares based on
   grid cell count)
