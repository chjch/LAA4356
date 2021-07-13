# Soils data from SSURGO (**S**oil **Sur**vey **G**e**o**graphic) Database

## 1. What is SSURGO?

- most detailed level of soil geographic data
- developed by the National Cooperative Soil Survey (NCSS) in accordance with NCSS standard
- hosted and maintained by the Natural Resources Conservation Service ([NRCS](https://www.nrcs.usda.gov/wps/portal/nrcs/site/national/home/)), an agency of U.S. Department of Agriculture (USDA)
- resource planning and analysis of soils data (national, regional, state-wide)
- FGDL detailed [metadata](https://fgdl.org/metadataexplorer/full_metadata.jsp?docId=%7B627D356C-7409-4339-A6BF-A2C7C23D7960%7D&loggedIn=false)

## 2. NICCDCD (Non-irrigated Capability Class, Dominant Condition)

| Class    | Description                                                                                                                                                                                               | Arability |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|  1  |  soils have few limitations that restrict their use.                                                                                                                                               | YES       |
|  2  |  soils have moderate limitations that reduce the choice of plants or that require moderate conservation practices.                                                                                 | YES       |
|  3  |  soils have severe limitations that reduce the choice of plants or that require special conservation practices, or both.                                                                           | YES       |
|  4  |  soils have very severe limitations that reduce the choice of plants or that require very careful management, or both.                                                                             | YES       |
|  5  |  soils are subject to little or no erosion but have other limitations, impractical to remove, that restrict their use mainly to pasture, <br>rangeland, forestland, or wildlife habitat.               | NO        |
|  6  |  soils have severe limitations that make them generally unsuitable for cultivation and that restrict their use mainly to pasture, <br>rangeland, forestland, or wildlife habitat.                      | NO        |
|  7  |  soils have very severe limitations that make them unsuitable for cultivation and that restrict their use mainly to <br>grazing, forestland, or wildlife habitat.                                      | NO        |
|  8  |  soils and miscellaneous areas have limitations that preclude commercial plant production and that restrict their use to <br>recreational purposes, wildlife habitat, watershed, or esthetic purposes. | NO        |

## 3. HYDGRPDCD (Hydrologic Group, Dominant Condition)

- Hydrologic soil groups are based on estimates of runoff potential. 
- Soils are assigned to one of four groups according to the rate of water infiltration when:
  - the soils are not protected by vegetation,
  - are thoroughly wet, and
  - receive precipitation from long-duration storms.
- The soils in the U.S. are assigned to four groups (A, B, C, and D) and three dual classes (A/D, B/D, and C/D).

| Group | Description                                                                                                                                                                                                                                                                                                                     | Water Transmission Rate |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|
| A     | Soils having a high infiltration rate (low runoff potential) when thoroughly wet. <br>These consist mainly of deep, well drained to excessively drained sands or gravelly sands.                                                                                                                                                    | high                    |
| B     | Soils having a moderate infiltration rate when thoroughly wet. <br>These consist chiefly of moderately deep or deep, moderately well drained or well drained soils that <br>have moderately fine texture to moderately coarse texture.                                                                                                  | moderate                |
| C     | Soils having a slow infiltration rate when thoroughly wet. <br>These consist chiefly of soils having a layer that impedes the downward movement of water or <br>soils of moderately fine texture or fine texture.                                                                                                                       | slow                    |
| D     | Soils having a very slow infiltration rate (high runoff potential) when thoroughly wet. <br> These consist chiefly of clays that have a high shrink-swell potential, soils that have a high water table, <br>soils that have a claypan or clay layer at or near the surface, and soils that are shallow over <br>nearly impervious material. | very slow               |

**_Note:_** If a soil is assigned to a dual hydrologic group (A/D, B/D, or C/D), the first letter is for drained areas and the second is for undrained areas. Only the soils that in their natural condition are in group D are assigned to dual classes.

## 4. WTDEPANNMIN (Water Table Depth, Annual, Minimum)

- the shallowest depth (from the surface) to a wet soil layer (water table)
- expressed as centimeters (cm)
- at any time during the year
