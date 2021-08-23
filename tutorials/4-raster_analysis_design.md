# Tutorial 4 - Spatial Analyst and Landscape Design with Raster Data

- [Tutorial 4 - Spatial Analyst and Landscape Design with Raster Data](#tutorial-4---spatial-analyst-and-landscape-design-with-raster-data)
  - [1. Introduction to Tools in Spatial Analyst](#1-introduction-to-tools-in-spatial-analyst)
    - [1.1 Extract by Attributes](#11-extract-by-attributes)
    - [1.2 Expand](#12-expand)
    - [1.3 Euclidean Distance](#13-euclidean-distance)
    - [1.4. Slice (a reclassification tool)](#14-slice-a-reclassification-tool)
  - [2. Raster Dataset Properties and Geoprocessing Environment](#2-raster-dataset-properties-and-geoprocessing-environment)
    - [2.1 Extent](#21-extent)
    - [2.2 Spatial Reference](#22-spatial-reference)
    - [2.3 Raster Information](#23-raster-information)
    - [2.4 Raster Processing Environment](#24-raster-processing-environment)
  - [3. The Pixel Editor](#3-the-pixel-editor)
    - [3.1 Preparation](#31-preparation)
    - [3.2 Interactively edit classified pixels](#32-interactively-edit-classified-pixels)
    - [3.3 Reclassify using information from a feature class](#33-reclassify-using-information-from-a-feature-class)

## 1. Introduction to Tools in Spatial Analyst

The Spatial Analyst extension for ArcGIS Pro provides a suite of tools and
capabilities for performing comprehensive, **_raster-based_** spatial analysis.
The [raster calculator](3-raster_geoprocessing.md#4-map-algebra) we introduced
in Tutorial 3 is an example of tools under the Spatial Analyst extension.
Here in this tutorial, we introduce three additional tools in Spatial Analyst:
_Extract by Attributes_, _Expand_, and _Euclidean Distance_.

### 1.1 Extract by Attributes

The [Extract by Attributes](https://tinyurl.com/dbmr3nhh) tool extracts the
cells **extracts** the cells of a raster based on a **_logical query_**.

- Example 1: extract a single value
  - Input raster: `lulc2015.tif`.
  - Where clause: `DESCRIPTIO = 'School'`.
- Example 2: extract multiple values
  - Input raster: `lulc2015.tif`.
  - Where clause: <code>DESCRIPTIO IN (
                        'Low Density Residential (0-4 du/ac)',
                        'Low Medium Density Residential (4-9 du/ac)',
                        'Mixed Commercial/Residential',
                        'High Density Residential (16+ dua/ac)',
                        'Medium Density Residential (9-16 du/ac)')
                  </code> OR
                  <code>VALUE >= 30 And VALUE <= 34</code>

### 1.2 Expand

The [Expand](https://tinyurl.com/379536y2) tool **_expands_** specified zones
of a raster by a specified number of cells.
You could think of "Expand" as the raster version of the
[_buffer_](2-learn_arcpro.md#31-finding-a-tool) tool we previously introduced
in Tutorial 2.
However, unlike the buffer tool which allows you to specify the distance, since
raster data are formed by cells (pixels), we must also specify distances in
terms of the number of cells.

- Input raster: `lulc2015.tif`.
- Number of cells: `20`.
- Zone values: `22, 23, 24, 25, 26`
- [Expand method](https://tinyurl.com/59dtcwjv): `Morphological`

### 1.3 Euclidean Distance

- Input feature source data: `BusStops.shp`.
- Cell size: `100`
- Distance method: Planer (2D plane) vs. Geodesic (3D ellipsoid) <br>
  <img alt="euc_dist" src="img/eucdist.gif" vspace="5px">

### 1.4. Slice (a reclassification tool)

The [Slice](https://tinyurl.com/4kyza4s) tool slices or **_reclassifies_** the
range of values of the input cells into zones of (a) _equal interval_ or
(b) _equal area_, or by (c) _natural breaks_.

- Input raster: _output of Euclidean Distance.
- Number of output zones: `9`.<br>
  <img alt="slice" src="img\slice.gif" vspace="5px">
- Slice Method:
  - `Equal interval` - Determines the range of the input values and divides
    the range into the specified number of output zones. (same range with each
    zone)
  - `Equal area` - Specifies that the input values will be divided into the
    specified number of output zones, with each zone having a similar number of
    cells. (same area with each zone)
  - [`Natural breaks`](https://tinyurl.com/4tnre3hm) - Natural Breaks classes
    are based on _natural groupings_ inherent in the data.
    Class breaks are identified that best group similar values and that
    maximize the differences between classes.
    Natural breaks are data-specific classifications and not useful for
    comparing multiple maps built from different underlying information.<br>
    <img alt="natural_breaks" src="img\naturalbreaks.png" vspace="5px">
- Base zone for output: `1`.

## 2. Raster Dataset Properties and Geoprocessing Environment

Recall we have learned the basics about the raster format in
[Tutorial 3](3-raster_geoprocessing.md#1-understand-data-in-the-raster-format).
Now, let's dive deeper to get a better understanding about
[Raster Dataset Properties](https://tinyurl.com/cw8fxab7).
In this section we will talk about (1) _extent_, (2) _spatial reference_ and
(3) _raster information_.

> :bulb: Where to see properties of a raster dataset?<br>
> You can access raster dataset properties through by <ins>right clicking</ins>
> the raster either in the **_Contents_** pane or the **_Catalog_** pane.

### 2.1 Extent

The Extent section describes the rectangle or boundary containing the raster
dataset.
The top, bottom, left, and right coordinates of the rectangle are listed in the
same spatial reference units in which the raster is stored.

### 2.2 Spatial Reference

To enable the data in each layer to integrate when displayed and queried, each
layer in a _map_ must reference locations on the earth's surface in a common
way.
Coordinate systems provide this framework.
There are, in general, two types of coordinate systems:
[GCS vs. PCS](https://tinyurl.com/y4ysskj3).<br>
<img alt="gcs_pcs" src="img/gcs_pcs.png" vspace="5px">

A spatial reference is the coordinate system used to store each feature class
and raster dataset, as well as other coordinate properties.
The raster dataset's coordinate system is described in the Spatial Reference
section.
All the spatial reference's parameters are listed.
A raster dataset can have an undefined coordinate system.

### 2.3 Raster Information

- Cell Size: determines how detailed or coarse of the information presented by
  the raster dataset.<br>
  <img alt="cell_size" src="img/cellSize.gif" vspace="5px">
- Source type (controls how the data is rendered by default):
  - Generic - Uses the application defaults for resampling and stretching.
  - Elevation - Applies bilinear resampling and a Min-Max stretch.
  - Thematic - Applies nearest neighbor resampling and a Standard Deviation
    stretch.
- Format: raster data can be stored and presented in many
  [formats](https://tinyurl.com/3pacpvzu).
  In ArcGIS Pro, _geodatabase raster_ is the native data structure.
  Another format that is very popular is Tagged Image File Format (TIFF) which
  does not require creating a File Geodatabase and can be read/write by many
  open-source GIS software.

### 2.4 Raster Processing [Environment](https://tinyurl.com/n6rfn2dp)

[Geoprocessing environment](https://tinyurl.com/2t5mt3w3) settings are in
effect, additional parameters that affect a tool's results.
They differ from normal tool parameters in that they don't appear on a tool's
dialog box (with certain exceptions).
Rather, they are values you set once using a separate dialog box and are
interrogated and used by tools when they are run.

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


- [Soils.shp](../datasets/soils.md)
- Value field: ```corsteel``` (Corrosion Steel): Susceptibility of uncoated steel to corrosion when in contact with the soil.

## 3. The Pixel Editor

Pixel Editor contains a set of tools used to interactively
**manipulate pixel values** for raster and imagery data.
It allows you to edit an individual pixel or a group of pixels at one time.
For the purpose of this studio, you may use the **Pixel Editor** to reclassify
pixels, namely changing the current land use of the area represented by those
pixels to _demonstrate your design ideas_.

### 3.1 Preparation

The output of _image classification_, a task of assigning classes to all
pixels in a (remotely sensed) image, is a _thematic classified raster dataset_.
The [LULC_2015](metadata/lulc/lulc.md) raster dataset is an output of such
image classification process, plus posterior adjustments based on features from
other vector data.
Due to these adjustments, the raster dataset lost the thematic characteristic.
Thus, the first step to use the Pixel Editor on _LULC_2015_ is to restore the
thematic property.

**Steps** (only needed when raster dataset is not thematic data):

1. Make a copy of the original raster dataset:
   [Copy Raster](https://tinyurl.com/25a4hem8)
2. Change the _Data Source_ type to **Thematic**:
   [Set Raster Properties](https://tinyurl.com/3j4uk8m5)

### 3.2 Interactively edit classified pixels

1. Select (click on) the raster layer in the _Contents_ pane.
2. Go to the **Imagery** tab.<br>
   ![imagery tab](img/imagery_tab.png)
3. Click on the **Pixel Editor** ![pixel editor](img/pixel_editor_icon.png).
4. In the **Edit** group, specify **_Current Class_** and **_New Class_**.
5. Three options:
   1. Reclassify Pixel ![reclassify pixel](img/reclassify_pixel_icon.png)
   2. Reclassify Object ![reclassify object](img/reclassify_object_icon.png)
   3. Reclassify Region ![reclassify region](img/reclassify_region_icon.png)

### 3.3 Reclassify using information from a feature class

In many occasions, information, such as shapes and boundaries, from a vector
layer can be used to guide your decisions on where should land-use changes
occur.
For example, the [taxlot](1-software_and_data.md#property) data containing
parcels that reflects property ownerships can be used as a reference to
determine the site of a proposed newly developed neighborhood.

1. Start a Pixel Editor session.
2. Use a feature to create your region.
3. Rasterize the region ![reclass feature](img/reclass_using_feature_icon.png).
4. Save your edits.
