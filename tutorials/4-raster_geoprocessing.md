### 1.4 Fundamental [Properties of a Raster Dataset](https://pro.arcgis.com/en/pro-app/latest/help/data/imagery/raster-dataset-properties.htm)

- Spatial Reference (projection): [GCS vs. PCS](https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/coordinate-systems-difference/)
<br> <img alt="gcs_pcs" src="img/gcs_pcs.png" vspace="5px">
- Extent: The top, bottom, left, and right coordinates of the rectangle (boundary) containing the raster dataset.
- Cell Size: determines how detailed or coarse of the information presented by the raster dataset. <br> <img alt="cell_size" src="img/cellSize.gif" vspace="5px">

## 2. Run Raster tools in ArcGIS Pro

### 2.1. [Polygon to Raster](https://pro.arcgis.com/en/pro-app/latest/tool-reference/conversion/polygon-to-raster.htm)

- Input data: [Soils.shp](../datasets/soils.md)
- Value field: ```corsteel``` (Corrosion Steel): Susceptibility of uncoated steel to corrosion when in contact with the soil.
- Cell assignment type: Maximum combined area. <br> <img alt="cell_assignment" src="img/cell_alignment.png" vspace="5px">

### 2.2. [Reclassify](https://pro.arcgis.com/en/pro-app/tool-reference/spatial-analyst/reclassify.htm) (reclassification)

- Input data: _output from **polygon to raster** tool_
- Reclass field: ```corsteel```
- Reclassification:

|            remap range                 |                remap value                 |
|:--------------------------------------:|:------------------------------------------:|
| ![remap_range](img/remap_range.gif) | ![remap_value](img/remap_value.gif)     |

### 2.3. [Euclidean Distance](https://pro.arcgis.com/en/pro-app/tool-reference/spatial-analyst/euclidean-distance.htm)

- Input data: [BusStops.shp](../datasets/transit.md)
- Cell size: _100 meter_
- Distance method: Planer (2D plane) vs. Geodesic (3D ellipsoid) <br> <img alt="euc_dist" src="img/eucdist.gif" vspace="5px">

### 2.4. [Slice](https://pro.arcgis.com/en/pro-app/tool-reference/spatial-analyst/slice.htm) (reclassification)

- Input data: _output of **Euclidean Distance** tool_ <br><img alt="slice" src="img\slice.gif" vspace="5px">

- Slice Method
  - **_Equal interval_**: Determines the range of the input values and divides the range into the specified number of output zones. (same range with each zone)
  - **_Equal area_**: Specifies that the input values will be divided into the specified number of output zones, with each zone having a similar number of cells. (same area with each zone)
  - [**_Natural breaks_**](https://www.spatialanalysisonline.com/HTML/index.html?classification_and_clustering.htm#:~:text=Natural+breaks%2FJenks): Natural Breaks classes are based on natural groupings inherent in the data.Class breaks are identified that best group similar values and that maximize the differences between classes. Natural breaks are data-specific classifications and not useful for comparing multiple maps built from different underlying information. <br> <img alt="natural_breaks" src="img\naturalbreaks.png" vspace="5px">

### 2.5. [Raster Calculator](https://pro.arcgis.com/en/pro-app/tool-reference/spatial-analyst/raster-calculator.htm)

- Input data: [elevation_ft.tif](../datasets/DEM/dem.md), [lulc2015.tif](../datasets/lulc/lulc.md)
- [Map Algebra Expression](https://pro.arcgis.com/en/pro-app/help/analysis/spatial-analyst/mapalgebra/working-with-operators.htm)
- Example functions:
  1. raise elevation by 10 feet.
  2. convert elevation from feet to meter (1 m = 3.28084 ft).
  3. get residential only from lulc.
  4. create a raster grid only contain elevation information for residential areas.

## 3. Raster Processing [Environment](https://pro.arcgis.com/en/pro-app/latest/tool-reference/environment-settings/an-overview-of-geoprocessing-environment-settings.htm)

General info about [Geoprocessing environment settings](https://pro.arcgis.com/en/pro-app/latest/tool-reference/environment-settings/what-is-a-geoprocessing-environment.htm).

"**_MESC_**" are the four most important environment settings for raster analysis.

- [Mask](https://pro.arcgis.com/en/pro-app/tool-reference/environment-settings/mask.htm): set by feature class or raster dataset <br> <img vspace="5px" src="img\mask.gif">
- [Extent](https://pro.arcgis.com/en/pro-app/tool-reference/environment-settings/output-extent.htm): set by feature class, raster dataset, or coordinates of the sides of the rectangle (Left, Right, Top, and Bottom). <br> <img vspace="5px" src="img\extent.png">
- [Snap raster](https://pro.arcgis.com/en/pro-app/tool-reference/environment-settings/snap-raster.htm): set by a raster dataset. <br> 
  |            no snapping raster            |            with snapping raster                |
  |:----------------------------------------:|:----------------------------------------------:|
  | ![snap_left](img/snapRaster_left.png) | ![snap_right](img/snapRaster_right.png)     |

- [Cell size](https://pro.arcgis.com/en/pro-app/tool-reference/environment-settings/cell-size.htm): set by a raster dataset or number.

Example:

1. Re-visit Euclidean Distance.
2. Set the mask.

Save a raster grid for sharing (not FGDB)
