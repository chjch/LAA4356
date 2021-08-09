# Tutorial 2 - Get to know ArcGIS Pro

- [Tutorial 2 - Get to know ArcGIS Pro](#tutorial-2---get-to-know-arcgis-pro)
  - [1. Create a Project in ArcGIS Pro](#1-create-a-project-in-arcgis-pro)
    - [1.1 Open ArcGIS Pro](#11-open-arcgis-pro)
    - [1.2 Create a new project](#12-create-a-new-project)
    - [1.3 The project home folder](#13-the-project-home-folder)
  - [2. ArcGIS Pro User Interface](#2-arcgis-pro-user-interface)
    - [2.1 Project Ribbon](#21-project-ribbon)
    - [2.2 Views](#22-views)
    - [2.3 Panes](#23-panes)
  - [3. Work with Symbology and Create a Layout](#3-work-with-symbology-and-create-a-layout)
    - [3.1 Add data to map view](#31-add-data-to-map-view)
    - [3.2 Create a _layout_](#32-create-a-layout)

## 1. Create a Project in ArcGIS Pro

ArcGIS Pro organizes your work into [projects](https://tinyurl.com/2r7vcje2).
A **project** is a collection of related items—_maps_, _layouts_, *tables*,
*charts*, *data connections*, and more—that contribute to a common purpose.
The purpose may be to (a) analyze a problem, (b) to visualize a state of
affairs, (c) to maintain or update a data model of infrastructure, or
something else.

### 1.1 Open ArcGIS Pro

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

### 1.2 Create a new project

Create a project using the **_Map_** template.

1. Specify the project name, e.g., *Tutorial_1*.
2. Choose a **folder** on your local drive to store the project.

### 1.3 The project home folder

- `Tutorial_1.aprx`: the _project file_ that you can **Double-click** to
  open the project.
- `Tutorial_1.gdb`: a [file geodatabase](https://tinyurl.com/4xtbkdc2), the
  [_default_](https://tinyurl.com/nm23t36r) workspace storing output data of
  [geoprocessing](https://tinyurl.com/3z98ewvf) tools.
- `Tutorial_1.tbx`: the default [Toolbox](https://tinyurl.com/5ef7jhfy) where
  new [_models_](https://tinyurl.com/usr7hktu) created in this project are
  going to be stored.

<img alt="proj_folder" vspace="5px" src="img/proj_folder.png">

> :bulb:<br>
> Remember to [Save a project](https://tinyurl.com/wh5u4e2r) frequently to
> avoid losing your works.

## 2. ArcGIS Pro User Interface

The main parts of the ArcGIS Pro [interface](https://tinyurl.com/4r2j9447) are
the **_ribbon_**, **_views_**, and **_panes_**.
ArcGIS Pro is a _ribbon-based_ application.
Many commands are available from the **ribbon** at the top of the ArcGIS Pro
window; more advanced or specialized functionality is found on panes
(dockable windows) that can be opened as needed.

### 2.1 Project Ribbon

ArcGIS Pro uses a horizontal ribbon at the top of the application window to
display and organize functionality into **<ins>a series of tabs</ins>**.
Some of these tabs (core tabs) are always present.
Others (contextual tabs) appear when the application is in a particular state.

- **Map** tab: basic mapping operations
- **Insert** tab: Adding new map, scene, or layout
- **Analysis** tab: Geoprocessing, ModelBuilder, Python and more

![ribbon](https://tinyurl.com/nm57ucyd)

### 2.2 Views

Views are windows for working with **_maps_**, **_scenes_**, **_tables_**,
**_layouts_**, and other presentations of data.
A project may have many views, which can be
<ins>opened and closed as needed</ins>.

| map view (2D)                             | scene view (3D)                             |
|:-----------------------------------------:|:-------------------------------------------:|
| ![map view](img/map_view.png)             | ![scene view](https://tinyurl.com/wj7xj49j) |

### 2.3 Panes

**Content Pane**:
The layers in a _map_ or _scene_ are listed in the
[Contents pane](https://tinyurl.com/seez74xb).
Use this pane to manage the display of **layers**, **symbology**, and other
**layer properties**.

- List by Drawing Order
- List by Data Source
- List by Selection

> :bulb:<br>
> These [keyboard shortcuts](https://tinyurl.com/ehhaahze) will improve your
> productivity when working with layers in the Content pane.

**Catalog Pane**:
The [Catalog pane](https://tinyurl.com/jmf9cuwx) has tabs across the top that
provide access to collections of items.

- **Maps** (default map): In ArcGIS Pro you can have multiple maps
  simultaneously to visualize and compare them side-by-side.
  The map concept is similar to [Data Frame](https://tinyurl.com/b4fydnms)
  in **_ArcMap_**.
- **Toolboxes**: shows toolboxes (default toolbox is automatically loaded).
- **Layouts**: if any created with the project.
- **Folders**: [Add Folder Connection](https://tinyurl.com/y9f499ym) allows you
  to quickly access existing folder on your computer in ArcGIS Pro.
- **Databases**: shows connected geodatabases

![panes](https://tinyurl.com/49mzxxmn)

## 3. Work with Symbology and Create a Layout

### 3.1 Add data to map view

- Add **study area** boundary
- Check out the **Attribute Table**
  (keyboard shortcut: <kbd>Ctrl</kbd>+<kbd>T</kbd>)
- Work with vector symbology: [census block](metadata/census/census.md)
- Work with raster symbology: [LULC ca. 2015](metadata/lulc/lulc.md)

### 3.2 Create a _layout_

A _page layout_ (often referred to simply as a
[**layout**](https://tinyurl.com/3j6m7e5p)) is a collection of map elements
organized on a virtual page designed for map **_printing_**.
Common map elements include one or more
[**map frames**](https://tinyurl.com/fxyjvn9s) (each containing an ordered set
of map layers), a **scale bar**, a **north arrow**, a map **title**,
descriptive text, and a **legend**.

1. Insert a new _layout_.
2. Add map frame to the layout.
3. Add a _scale bar_, a _legend_, and a _north arrow_.

This video below created by ESRI gives a higher-level overview related to
basic functions and operations about the Layout.

<a href="https://www.youtube.com/watch?v=NZ9ei4-23MM">
  <img src="img/layout_video_timg.png" alt="ahp video" width="800">
</a>
