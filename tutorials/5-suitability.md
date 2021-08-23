# Tutorial 5 - Creating Contour Maps and the Suitability Analysis Workflow

- [Tutorial 5 - Creating Contour Maps and the Suitability Analysis Workflow](#tutorial-5---creating-contour-maps-and-the-suitability-analysis-workflow)
  - [2. Create a Contour Map](#2-create-a-contour-map)
    - [2.1 The Contour geoprocessing tool](#21-the-contour-geoprocessing-tool)
    - [2.2 Working with symbology and label](#22-working-with-symbology-and-label)

## 2. Create a Contour Map

Contours are lines that connect locations of equal value in a raster dataset
that represents continuous phenomena such as **_elevation_**, _temperature_,
_precipitation_, _pollution_, or _atmospheric pressure_.
The line features connect cells of a constant value in the input.

> :bulb:<br>
> Contour lines are often generally referred to as isolines.
> In terms of elevation, the areas where the contours are closer together
> indicate the steeper locations.

### 2.1 The Contour geoprocessing tool

- _Input data_: [elevation_ft.tif](metadata/DEM/dem.md)
- _Geoprocessing tool_: [Contour (Spatial Analyst)](https://tinyurl.com/d9rkh598)
- _Parameters_
  - Contour Interval: **1**
  - Base contour: **0**
  - Z factor: **0.3048**
  - Contour type: **Contour**

### 2.2 Working with symbology and label

- Use color scheme: _Red-Yellow-Blue_
- Add labels to contour map

<img src="img/contour_map.png" alt="contour map" width=650>