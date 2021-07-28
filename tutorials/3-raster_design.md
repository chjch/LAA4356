# Tutorial 3 - Landscape Design with Raster Data

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

## 2. The Pixel Editor

