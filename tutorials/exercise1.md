# Test Drive on Overlay Analysis

Recall the _taxlot.shp_ introduced in
[Tutorial 1](1-software_and_data.md#property).
The _shapefile_ dataset contains three fields in its attribute table:
ACTYBLT (actual year built), JV (just or market value of the parcel),
DORUC (land use code).

Create three raster datasets with the following criteria.

- `'ACTYRBLT' < 1990`
- `'JV' < 100000`
- `'DORUC' >= '002'`

On a single sheet of paper, type/write your name, the class title and the date
in the upper right hand corner. Then, please answer the following questions:

1. How many 5m grid cells are out of the FEMA 100 year floodplain and outside of a 5% slope?  
2. How many hectares meet your criteria? (i.e. calculate hectares based on grid cell count)
