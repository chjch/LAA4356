# Tutorial 5 - Suitability Analysis Workflow and Creating Contour Maps

- [Tutorial 5 - Suitability Analysis Workflow and Creating Contour Maps](#tutorial-5---suitability-analysis-workflow-and-creating-contour-maps)
  - [1. The General Workflow of Suitability Analysis](#1-the-general-workflow-of-suitability-analysis)
    - [1.1 Define Criteria](#11-define-criteria)
    - [1.2 Transform to a common suitability scale](#12-transform-to-a-common-suitability-scale)
    - [1.3 Weight the criteria and create a suitability map](#13-weight-the-criteria-and-create-a-suitability-map)
  - [2. Locate Regions](#2-locate-regions)
  - [3. Create a Contour Map](#3-create-a-contour-map)
    - [3.1 The Contour geoprocessing tool](#31-the-contour-geoprocessing-tool)
    - [3.2 Working with symbology and label](#32-working-with-symbology-and-label)

## 1. The General Workflow of Suitability Analysis

**Suitability** is a measure of the *relative degree* to which a land unit is
suitable for a <ins>specified purpose</ins>.
The decision on suitability is based strictly on its **current condition** and
**the context** in which it is found.
It neither anticipates nor requires any change for the assignment of a
suitability score.
Suitability modeling is the process of determining **_suitability_**.
Its output is usually presented in the form of a **suitability map**.

In this tutorial, we will use the tools we have learned so far to create a
suitability model from scratch.

### 1.1 Define Criteria

The first step to create a suitability model is to identify the criteria for
the subject of the model.
Each criterion identified should be instrumental in reaching the overall goal
of the model.
For example, if we want to measure suitability for **high-density** (greater
than 20 units per acre) **residential** development.

- Low susceptibility of concrete to corrosion when in contact with the soil.
- Alternative transport solution.
- Good accessibility to parks and recreational areas.
- The surface is relatively flat.

The following table summarizes how we can quantify the above criteria.

| Dataset      | Field  | Value  | Geoprocessing                              |
|--------------|--------|--------|--------------------------------------------|
| Soils.shp    | corcon | n/a    | Polygon to Raster                          |
| BusStops.shp | n/a    | n/a    | Euclidean Distance                         |
| slope_ps     | n/a    | n/a    | Slice + Reclassify                         |
| lulc2015.tif | n/a    | 37, 40 | Extract by Attributes + Euclidean Distance |

### 1.2 Transform to a common suitability scale

All three criteria described above influence, although in different magnitudes,
how a piece of land unit is suitable for a proposed high-density residential
development.
Therefore, to determine suitability for orchards, we need to combine these
criteria in _a meaningful way_.
However, in this case, and virtually all suitability analyses, criteria are
measured in **different** [measurement levels](https://tinyurl.com/jh8n7hzh),
i.e., nominal, ordinal, interval, and ratio at different scales.
Hence, transformation is needed for each criterion from its original scale to
<ins>a common suitability scale</ins>.

In general, there are 3 transformation methods:

- **Unique categories**: is a one-to-one matching of the criterion value to
  the suitability value and best for _nominal_ and _ordinal_ data.
  As an example, the table below describes this type of transformation applied
  to **_Criterion 1_**.
  |  corcon  | old value | new value |
  |----------|-----------|-----------|
  | (empty)  | 2         | 1         |
  | High     | 4         | 4         |
  | Moderate | 3         | 7         |
  | Low      | 1         | 9         |
- **Range of classes**: is applied when ranges of values can be grouped into
  _homogeneous_ classes that can be assigned the same suitability preference.
  It is usually used for _interval_ and _ratio_ data.
  As an example, the table below describes this type of transformation applied
  to **_Criterion 2_**.
  | old value         | new value |
  |-------------------|-----------|
  | below 640<b>*</b> | 9         |
  | 640-1200          | 7         |
  | 1200-2000         | 3         |
  | above 2000        | 1         |
  > <b>*</b>: assuming 1.33 m/s, or **80 m/min** (source: Public transport
  > accessibility level - PTAL methodology developed by
  > **Transport for London**).
  >
  Another method we can use to do this kind of transformation is by using
  the [Slice](tutorials/4-raster_analysis_design.md#14-slice-a-reclassification-tool)
  tool we talked about in the last tutorial.
  We will apply **_Natural Breaks_** classification to the slope surface.
  Note that, since Slice returns values based on the input layer (higher input
  value gets higher reclassified value), we need to perform a Reclassify to
  make sure flatter areas get higher suitability scores.
- **Continuous functions**: applies linear or nonlinear functions to transform
  the values continuously to the suitability scale.
  Because this method applies a continuous function to the criterion values,
  with each increase in the criterion value, the resulting suitability value
  continuously changes.
  It is best for criteria represented by _ratio_ (or continuous) data such as
  slope, aspect, or distance.
  - Geoprocessing: <a id="rescale">`Rescale by Function`</a>.
  - Transformation: `Linear`.
  - From scale: `9`.
  - To scale: `1`.
  > :bulb: The "from scale" is greater than the "to scale" for a negative
  > linear relationship.

| original                      | transformed                                  |
|-------------------------------|----------------------------------------------|
| ![distance](img/distance.svg) | ![transformed](img/transformed_distance.svg) |

### 1.3 Weight the criteria and create a suitability map

To merge the criteria, we need to assign weights to them.
Note that, no matter what weight you give to a criterion individually, the sum
of total weights for all criteria should be equal to "1" or "100%".
You can pick up the weights based on relevant literature or your own knowledge
or preferences about the subject.
For example, 30%, 30%, and 40% for the each criteria described above
respectively.

Here, we introduced a so-called rank sum method to help you determine weights.
It is a simple method to assign weights by arranging the criteria (layers) in
**rank order** where the value 1 signifies most important, 2 next important,
and so on, to the nth important criteria.
The following equation and table explains how the method works.

<p align="center">
  <img src="img/rank_sum.svg" alt="rank sum">
</p>

| Criterion | rank | inverse ranking | weight   |
|-----------|------|-----------------|----------|
| soil      | 4    | 1               | 1/10=0.1 |
| transit   | 3    | 2               | 2/10=0.2 |
| slope     | 1    | 4               | 4/10=0.4 |
| park      | 2    | 3               | 3/10=0.3 |

Now, we can use the [weighted sum](https://tinyurl.com/33cjevph) tool to
overlay (multiplying each by their given weight and summing them together)
multiple criteria.

## 2. Locate Regions

After conducting a suitability analysis (obtaining a suitability map), we need
to go back to the goal, that is finding suitable sites for a specified land
use.
This process of finding suitable sites (areas) is generally referred to as
allocation.
Fortunately, with recent developments in ArcGIS Pro, we are offered a new tool
just for this purpose.

The [Locate Regions](https://tinyurl.com/6cx7unub) tool identifies the best
regions, or groups of contiguous cells, from an input utility (**suitability**)
raster that satisfies a specified evaluation criterion and that meet identified
shape, size, number, and inter-region distance constraints.

This tool uses a parameterized
[region-growing](https://en.wikipedia.org/wiki/Region_growing) (PRG) algorithm
to grow candidate regions from seed cells by adding neighboring cells to the
region that best preserves the specified shape but also maximizes utility for
the region.

- Total area: `50`.
- Area units: `Acres`
- Number of regions: `6`.
- Region shape: `square`.
- Region minimum area: `4`.
- Region maximum area: `10`.

Check out this [link](https://tinyurl.com/ywuud5zp) to learn more about the
Region Growing algorithm used by the Locate Regions tool.

## 3. Create a Contour Map

Contours are lines that connect locations of equal value in a raster dataset
that represents continuous phenomena such as **_elevation_**, _temperature_,
_precipitation_, _pollution_, or _atmospheric pressure_.
The line features connect cells of a constant value in the input.

> :bulb:<br>
> Contour lines are often generally referred to as isolines.
> In terms of elevation, the areas where the contours are closer together
> indicate the steeper locations.

### 3.1 The Contour geoprocessing tool

- _Input data_: [elevation_ft.tif](metadata/DEM/dem.md)
- _Geoprocessing tool_: [Contour (Spatial Analyst)](https://tinyurl.com/d9rkh598)
- _Parameters_
  - Contour Interval: **1**
  - Base contour: **0**
  - Z factor: **0.3048**
  - Contour type: **Contour**

### 3.2 Working with symbology and label

- Use color scheme: _Red-Yellow-Blue_
- Add labels to contour map

<img src="img/contour_map.png" alt="contour map" width=650>