# Tutorial 3 - Landscape Design with Raster Data

- [Tutorial 3 - Landscape Design with Raster Data](#tutorial-3---landscape-design-with-raster-data)
  - [1. Understand Data in the Raster Format](#1-understand-data-in-the-raster-format)
    - [1.1 Single-band raster dataset](#11-single-band-raster-dataset)
    - [1.2 Multiple-band raster dataset](#12-multiple-band-raster-dataset)
    - [1.3 Comparison between display in single band and multi-band](#13-comparison-between-display-in-single-band-and-multi-band)
  - [2. Create a Contour Map](#2-create-a-contour-map)
    - [2.1 The Contour geoprocessing tool](#21-the-contour-geoprocessing-tool)
    - [2.2 Working with symbology and label](#22-working-with-symbology-and-label)
  - [3. The Pixel Editor](#3-the-pixel-editor)
    - [3.1 Preparation](#31-preparation)
    - [3.2 Interactively edit classified pixels](#32-interactively-edit-classified-pixels)
    - [3.3 Reclassify using information from a feature class](#33-reclassify-using-information-from-a-feature-class)

## 1. Understand Data in the Raster Format

<img align="right" src="https://tinyurl.com/zr3muyc5">

In its simplest form, a raster consists of **a matrix of cells** (or pixels)
organized into _rows_ and _columns_ (or a grid) where
<ins>each cell contains a value</ins> representing information, such as
temperature.
Raster grids can be outputs from raster analysis, digital aerial photographs,
imagery from satellites, digital pictures, or even scanned maps.

Data stored in a raster format represents **real-world phenomena**.

### 1.1 Single-band raster dataset

Values in a single-band raster dataset may represent temperature, elevation,
soil pH value, etc.
The three main ways to display single-band raster datasets are shown below.

- using two colors (binary)
- grayscale
- color map

<img src="img\raster_colormap.gif">

### 1.2 Multiple-band raster dataset

<img align="right" src="img\rasterbands.png">

When there are _multiple bands_, every cell location has more than one value
associated with it.
A satellite image, for example, commonly has multiple bands representing
different wavelengths from the _ultraviolet_ through the _visible_ and
_infrared_ portions of the electromagnetic spectrum.
For example, the aerial photo (or basemap) of the study area,
[orthoNAIP1.tif](1-software_and_data.md#2-introduction-to-the-gis-datasets),
is a **3-band** [orthophoto](https://tinyurl.com/y4w7xp54) that is acquired
from both aircraft (using digital camera) and satellite imagery.
The three bands are RGB stands for red, green, and blue respectively.
The RGB composite can display the raster dataset in **natural color**.

![rgb composite](img/rgb_composite.gif)

> :bulb: The term **_band_** originated from the reference to the _color band_
> on the electromagnetic spectrum.

### 1.3 Comparison between display in single band and multi-band

|    single-band satellite image     |    3-band RGB composite satellite image    |
|:----------------------------------:|:------------------------------------------:|
| ![grayscale](img/grayscale.png)    | ![rgb_composite](img/rgb_composite.png)    |

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
