# Tutorial 2 - Get to know ArcGIS Pro

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

- **Project File** (`*.aprx`): _Double-click_ to open the project.
- [File GeoDatabase](https://tinyurl.com/4xtbkdc2) (`*.gdb`):
  [_default_](https://tinyurl.com/nm23t36r) workspace for storing output
  data of [geoprocessing](https://tinyurl.com/3z98ewvf) tools.
- [Toolbox](https://tinyurl.com/5ef7jhfy) (`*.tbx`): New
  [_models_](https://tinyurl.com/usr7hktu) are stored in this default toolbox
  of the project. <br>
  <img alt="proj_folder" vspace="5px" src="img/proj_folder.png">

> :bulb:<br>
> Remember to [Save a project](https://tinyurl.com/wh5u4e2r) frequently to
> avoid losing your works.

## 2. Getting to know the [User Interface](https://tinyurl.com/4r2j9447)

### 2.1 Project Ribbon

- **Map** tab: basic mapping operations
- **Insert** tab: Adding new map, scene, or layout
- **Analysis** tab: Geoprocessing, ModelBuilder, Python and more

### 2.2 Content Pane

- List by Drawing Order
- List by Data Source
- List by Selection

### 2.3 Views

Views are windows for working with **_maps_**, _scenes_, _tables_, _layouts_,
and other presentations of data.
A project may have many views, which can be opened and closed as needed.

### 2.4 Catalog Pane

- **Maps** (default map): In ArcGIS Pro you can have multiple maps
  simultaneously to visualize and compare them side-by-side.
  The map concept is similar to [Data Frame](https://tinyurl.com/b4fydnms)
  in **_ArcMap_**.
- **Toolboxes**: shows toolboxes (default toolbox is automatically loaded).
- **Layouts**: if any created with the project.
- **Folders**: [Add Folder Connection](https://tinyurl.com/y9f499ym) allows you
  to quickly access existing folder on your computer in ArcGIS Pro.
- **Databases**: shows connected GeoDatabases

## 3. Add Data to Map and work with symbology

- Add Study area boundary
- Check out the **Attribute Table**
  (keyboard shortcut: <kbd>Ctrl</kbd>+<kbd>T</kbd>)
- Work with vector symbology: census block
- Work with raster symbology: LULC ca. 2015
