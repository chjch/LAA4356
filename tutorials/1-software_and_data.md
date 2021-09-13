# Tutorial 1 - Software setup and introduction to datasets

- [Tutorial 1 - Software setup and introduction to datasets](#tutorial-1---software-setup-and-introduction-to-datasets)
  - [1. Install ArcGIS Pro](#1-install-arcgis-pro)
  - [2. Introduction to the GIS datasets](#2-introduction-to-the-gis-datasets)
  - [3. Create a Project in ArcGIS Pro](#3-create-a-project-in-arcgis-pro)
    - [3.1 Open ArcGIS Pro](#31-open-arcgis-pro)
    - [3.2 Create a new project](#32-create-a-new-project)
    - [3.3 The project home folder](#33-the-project-home-folder)

## 1. Install ArcGIS Pro

- **Step 1 - Download**: Follow the instruction on
  https://www.geoplan.ufl.edu/software/arcgis-pro/ to obtain a copy of the
  software.
  Make sure you download the latest version i.e., ArcGIS Pro 2.8.
  The file is located inside `AGP2.8` with a name of `ArcGISPro_28_177688.exe`.
- **Step 2 - Install**: Double-click the installation file you just downloaded
  from last step, follow the instructions to install the application on your
  computer.
- **Step 3 - Open the software**: Find the software in your start menu just as
  any other existing program on your computer.
  You can either locate it in the App list under **ArcGIS** or search for
  **ArcGIS Pro** using the Search button on your taskbar.
- **Step 4 - Log in**:  Follow the instruction on
  https://www.geoplan.ufl.edu/software/esri-login-instructions/ to login to
  ArcGIS Pro.

> :memo: **_Make sure ArcGIS Pro is up-to-date_** <br>
> If you already have ArcGIS Pro installed on your computer before, please
> **make sure that you have the same version** as described above.
> If not, please update the application. An _software update_ notification will
> **automatically** pop out, every time you start the software (with internet
> connection).
> Otherwise, you can go to the [_About_](https://tinyurl.com/36v9vyw4) section
> in the [**Settings**](https://tinyurl.com/yy2w7f24)
> ![settings](img/settings_icon.png) to manually check for update.

## 2. Introduction to the GIS datasets

- **Download** from this [Dropbox link](https://tinyurl.com/85tjxnvh)
  (password provided separately).
- Critical to be aware and acquainted with what's available.
- Identifying and acquiring useful datasets is an essential skill.
- Understanding the concepts behind different types of GIS data.
  - vector: object view (discrete)
  - raster: field view (continuous)
  - "People manipulate object but cultivate field" (Couclelis, 1992).

| Theme | ID | File Name            | Data Format | Type | Description                                               |
|-------|----|----------------------|-------------|------|-----------------------------------------------------------|
| [Demography](metadata/census/census.md) | 1 <br> 2 | CensusBlocks_2010 <br> CensusTracts_2010 | vector <br> vector  | polygon <br> polygon   | 2010 [Census](https://www2.census.gov/geo/pdfs/reference/geodiagram.pdf) blocks <br> 2010 Census tracts |
| [Zoning & FLU](metadata/zoning_flu.md) | 3 <br> 4 <br> 5 | ApopkaZoning <br> Zoning <br> FutureLandUse | vector <br> vector <br> vector | polygon <br> polygon <br> polygon | [City of Apopka zoning ordinance](https://library.municode.com/fl/apopka/codes/code_of_ordinances?nodeId=PTIIILADECO_ART3ZODI_S3.1GEPR) <br> [Orange County zoning ordinance](https://library.municode.com/fl/orange_county/codes/code_of_ordinances?nodeId=PTIIORCOCO_CH38ZO_ARTIVZODIESZOMA) <br> [Orange County Future Land Use](https://www.orangecountyfl.net/PlanningDevelopment/ComprehensivePlanning.aspx#.X87_PGhKj-g)                                      |
| Boundaries | 6 <br> 7 <br> 8 <br> 9 | Jurisdiction <br> StudyArea <br> PublicFacilities <br> PublicLand | vector <br> vector <br> vector <br> vector | polygon <br> polygon <br> polygon <br> polygon | Apopka jurisdiction map <br> Study area boundary (partitioned into three sections) <br> Orange county roads, drainage, water/waste reclaimation <br> Public land (federal, state, county, municipal, etc.) |
| <p id="critical_zones"> Critical Zones </p>  | 10 <br> 11 <br> 12 <br> 13 | Conservation <br> dfirm_fldhaz_oct20 <br> histUndBus <br> wetlands | vector <br> vector <br> vector <br> vector | polygon <br> polygon <br> polygon <br> polygon | Conservation areas <br> [FEMA flood zones](https://www.fgdl.org/metadata/metadata_archive/fgdl_html/dfirm_fldhaz_apr08.htm) <br> Historically underutilized business zones <br> National wetland inventory                                      |
| [Transit](metadata/transit.md) | 14 <br> 15 | BusRoutes <br> BusStops           | vector <br> vector   | line <br> point  | Bus routes ([LYNX](https://www.golynx.com/corporate-info/facts-glance.stml) data) <br> Bus stops (LYNX data) |
| Transport | 16 <br> 17 | rail <br> Streets | vector <br> vector | line <br> line | Railroads in the study area <br> [Street network](metadata/FUNCLASS.md) of the study area |
| <a href="https://colab.research.google.com/drive/1dTJGRo9QLDyEhTLOQJDUw_F0UfnZUivM?authuser=1" rel="nofollow" id='property'>Property</a> | 18 <br> 19 | taxlot <br> MSBFP | vector <br> vector | polygon <br> polygon | [FGDL](https://www.fgdl.org/metadataexplorer/full_metadata.jsp?docId=%7B147B34F0-9E64-49AE-8B7F-5C4999BEC541%7D&loggedIn=false) Property parcel <br> [Microsoft Building Footprint](https://github.com/Microsoft/USBuildingFootprints) |
| Transport | 16 <br> 17 | rail <br> Streets | vector <br> vector | line <br> line | Railroads in the study area <br> Street network of the study area |
| <a href="https://colab.research.google.com/drive/1dTJGRo9QLDyEhTLOQJDUw_F0UfnZUivM#scrollTo=P6FJ8mMUy5Pj" rel="nofollow" id='property'>Property</a> | 18 <br> 19 | taxlot <br> MSBFP | vector <br> vector | polygon <br> polygon | [FGDL](https://www.fgdl.org/metadataexplorer/full_metadata.jsp?docId=%7B147B34F0-9E64-49AE-8B7F-5C4999BEC541%7D&loggedIn=false) Property parcel <br> [Microsoft Building Footprint](https://github.com/Microsoft/USBuildingFootprints) |
| [LULC](metadata/lulc/lulc.md) | 20 <br> 21 | LULC_2015 <br> CLC_LULC | raster <br> vector    | grid <br> polygon | Land Use Land Cover ca. 2015 <br> Cooperative Land Cover (Version 3.3)|
| [Soils](metadata/soils.md) | 22 <br> 23 <br> 24 <br> 25 | Soils <br> soil_agcl <br> soil_hgrp <br> soil_wt | vector <br> raster <br> raster <br> raster | polygon <br> grid <br> grid <br> grid | [SSURGO](https://www.nrcs.usda.gov/wps/portal/nrcs/detail/soils/survey/?cid=nrcs142p2_053627) soil polygons <br> Non-irrigated land capability class <br> Hydrologic soils group <br> Depth to water table (feet, classed)     |
| [Topography](metadata/DEM/dem.md) | 26 <br> 27 <br> 28 <br> 29 | elevation_ft <br> aspect <br> hillshade <br> slope_ps | raster <br> raster <br> raster <br> raster | tiff <br> tiff <br> grid <br> grid | Elevation 10m DEM (in feet) <br> Aspect in degrees <br> Hillshade (azimuth 315, altitude 45) <br> Slope (percent rise)  |
| Aerial Photo | 30 | orthoNAIP      | raster    | tiff        | 2015 [National Agriculture Imagery Program](https://www.fsa.usda.gov/programs-and-services/aerial-photography/imagery-programs/naip-imagery/) (NAIP)   |

## 3. Create a Project in ArcGIS Pro

ArcGIS Pro organizes your work into [projects](https://tinyurl.com/2r7vcje2).
A **project** is a collection of related items—_maps_, _layouts_, *tables*,
*charts*, *data connections*, and more—that contribute to a common purpose.
The purpose may be to (a) analyze a problem, (b) to visualize a state of
affairs, (c) to maintain or update a data model of infrastructure, or
something else.

### 3.1 Open ArcGIS Pro

The [Start page](https://tinyurl.com/5jdkbk64) consists of three sections
(columns).

1. The **Open** section: shows projects created recently.
   You can also choose to
   [**Open a project**](https://tinyurl.com/yv24vema).
2. The **New** section: shows the [templates](https://tinyurl.com/jscpxv9f)
   you can use to [Create a project](https://tinyurl.com/2yy9mt9r).
   - **_Map_**: working with 2D data (ArcMap).
   - **_Local_** and **_Global Scene_**: working with 3D data
      (ArcScene and ArcGlobe).
   - **_Catalog_**: Data management (ArcCatalog).
3. The **Resources** section: include links to blogs, tutorials, documentation,
   and highlights of recent development of the software.

### 3.2 Create a new project

Create a project using the **_Map_** template.

1. Specify the project name, e.g., *Tutorial_1*.
2. Choose a **folder** on your local drive to store the project.

### 3.3 The project home folder

- `Tutorial_1.aprx`: the _project file_ that you can **Double-click** to
  open the project.
- `Tutorial_1.gdb`: a [file geodatabase](https://tinyurl.com/4xtbkdc2), the
  [_default_](https://tinyurl.com/nm23t36r) workspace storing output data of
  [geoprocessing](https://tinyurl.com/3z98ewvf) tools.
- `Tutorial_1.tbx`: the default [Toolbox](https://tinyurl.com/5ef7jhfy) where
  new [_models_](https://tinyurl.com/usr7hktu) created in this project are
  going to be stored.

<img alt="proj_folder" vspace="5px" src="img/proj_folder.png">

> :bulb: Don't lose your hard work.<br>
> Remember to [Save a project](https://tinyurl.com/wh5u4e2r) frequently to
> avoid losing your works.
