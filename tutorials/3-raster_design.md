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

Values in a single-band raster dataset can be used to represent temperature,
elevation, soil pH value, etc.
The three main ways to display single-band raster datasets are shown below.

- using two colors (binary)
- grayscale
- color map

<img src="img\raster_colormap.gif">

### 1.2 Multiple-band raster dataset

and [RGB composite](https://desktop.arcgis.com/en/arcmap/10.3/manage-data/raster-and-img/renderers-used-to-display-raster-data.htm#ESRI_SECTION2_6DA80CD25C02461BBD61A752F92D2E6D)

- different wavelengths from the ultraviolet through the visible and infrared portions of the electromagnetic spectrum <br> <img vspace="5px" src="img\rgb_composite.gif">
- example: ```orthoNAIP1.tif```

> :bulb: The term **_band_** originated from the reference to the _color band_
> on the electromagnetic spectrum.

### 1.3 Comparison

|    single-band satellite image     |    3-band RGB composite satellite image    |
|:----------------------------------:|:------------------------------------------:|
| ![grayscale](img/grayscale.png)    | ![rgb_composite](img/rgb_composite.png)    |

## 2. The Pixel Editor

