# Zoning and Future Land Use

**_[Question: What is the difference between Zoning and Future Land Use (FLU)?](Q1_zoning_flu.md)_**

## 1. Apopka Zoning Code

- File name: ```ApopkaZoning.shp```
- Field name: ```Zoning```

| District                            | Zoning Code | Description                                  |
|-------------------------------------|-------------|----------------------------------------------|
| Residential                   | ZIP <br> AG <br> AG-E <br> RCE-1 <br> RCE-2 <br> R-1AA <br> R-1AAA <br> R-1 <br> R-1A  <br> R-2 <br> R-3 <br> MHP <br> MHS | Zoning In Progress <br> Agriculture <br> Agriculture Estate <br> Residential Country Estates 1 <br> Residential Country Estate 2 <br> Residential Single-Family <br> Residential Single-Family <br> Residential Single-Family <br> Residential Single-Family <br> Residential One- and Two-family <br> Residential Multiple-Family <br> Mobile Home Park District <br> Mobile Home Subdivision |
| Commercial Districts          | CN <br> C-1 <br> PO/I <br> C-2 <br> C-3 | Commercial Neighborhood <br> Retail Commercial <br> Professional Office/Institutional <br> General Commercial <br> Wholesale Commercial |
| Industrial Districts          | I-1 <br> I-2       | Restricted Industrial <br> General Industrial |
| Special Purpose Districts     | Mixed-CC <br> Mixed-EC <br> PR  | Mixed-Use Community Center <br> Mixed-Use Employment Center <br> Parks and Recreation |
| Planned Development Districts | PUD         | Planned Unit Development                     |
| Overlay Districts             | n/a <br> n/a | Historic District <br> Downtown Development Overlay Zoning District |

_[Source: City of Apopka Code of Ordinances](https://library.municode.com/fl/apopka/codes/code_of_ordinances?nodeId=PTIIILADECO_ART1GEPR_S1.8TRPR_1.8.1TRNEZODI)_

## 2. Orange County Zoning Code (Zoning_Oboundry.shp)

- File name: ```Zoning_OBoundary.shp```
- Field name: ```Zoning```
- Note: ```City``` (zoning defers to the city)

| District               | Zoning Code | Description                         |
|------------------------|-------------|-------------------------------------|
| Agricultural           | A-1 <br> A-2 <br> A-R | Citrus Rural District <br> Farmland Rural District <br> Agricultural-Residential District |
| Residential            | R-CE <br> R-CE-2 <br> R-CE-5 <br> R-1, R-1A & R-1AA <br> R-1AAA & R-1AAAA <br> R-2 <br> R-3 <br> X - C <br> R-T <br> R-T-1 <br> R-T-2 <br> R-L-D <br> UR-3 | Country Estate District  <br> Rural Residential District  <br> Rural Country Estate Residential District  <br> Single-Family Dwelling Districts  <br> Residential Urban District<br> Residential District<br> Multiple-Family Dwelling District<br> Cluster District (where X is the base zoning district) <br> Mobile Home Park District  <br> Mobile Home Subdivision District  <br> Combination Mobile Home and  Single-Family Dwelling District  <br> Residential Low-Density District<br> University Residential District |
| Non-residential        | P-O <br> C-1 <br> C-2 <br> C-3 <br> I-1A <br> I-1 / I-5 <br> I-2 / I-3 <br> I-4 <br> M-1 | Professional Office District <br> Retail Commercial District <br> General Commercial District <br> Wholesale Commercial District <br> Restricted Industrial District <br> Industrial District (Light) <br> Industrial District (General) <br> Industrial District (Heavy) <br> Property shall be rezoned to an appropriate zoning district that is consistent with the FLUM. |
| Other                  | NR <br> NC <br> NAC <br> X - PD <br> U-V | Neighborhood Residential <br> Neighborhood Center <br> Neighborhood Activity Corridor <br> Planned Development District (where X is the base zoning district) <br> Urban Village District |

_[Source: Orange County Code of Ordinances](https://library.municode.com/fl/orange_county/codes/code_of_ordinances?nodeId=PTIIORCOCO_CH38ZO_ARTIVZODIESZOMA)_

## 3. Future Land Use

- File name: ```FutureLandUse.shp```
- Field name: ```Label```
- Note: ```City``` (future land use defers to the city)

| Future Land Use Code | Description                                                                    |
|----------------------|--------------------------------------------------------------------------------|
| R                    | Rural / Agricultural (maximum 1 dwelling unit/10 acres and Agriculture)        |
| RSLD                 | Rural Settlement Low Density (maximum 2 dwelling units/acre)                   |
| RS 1/1               | Rural Settlement 1/1 (maximum 1 dwelling unit/acre)                            |
| RS 1/2               | Rural Settlement 1/2 (maximum 1 dwelling unit/2 acres)                         |
| RS 1/5               | Rural Settlement 1/5 (maximum 1 dwelling unit/5 acres)                         |
| LDR                  | Low Density Residential (up to 4 dwelling units/acre)                          |
| LMDR                 | Low-Medium Density Residential (up to 10 dwelling units/acre)                  |
| MDR                  | Medium Density Residential (up to 20 dwelling units/acre)                      |
| HDR                  | High Density Residential (up to 50 dwelling units/acre)                        |
| O                    | Office                                                                         |
| INST                 | Institutional                                                                  |
| EDU                  | Educational                                                                    |
| C                    | Commercial                                                                     |
| ACMU                 | Activity Center Mixed Use (International Drive)                                |
| ACR                  | Activity Center Residential (International Drive)                              |
| NAC                  | Neighborhood Activity Corridor                                                 |
| NC                   | Neighborhood Center                                                            |
| NR                   | Neighborhood Residential                                                       |
| CVC                  | Community Village Center (Four Corners – not available after September 2009)   |
| TND                  | Traditional Neighborhood Development (Avalon Park)                             |
| GC                   | Growth Center                                                                  |
| I (IND)              | Industrial                                                                     |
| CONS                 | Conservation                                                                   |
| PR/OS                | Parks and Recreation / Open Space                                              |
| WB                   |  Water Body                                                                    |
| PRES                 | Preservation                                                                   |
| V                    | Village – Horizon West                                                         |
| MUC                  | Mixed Use Corridor                                                             |
| MXDAC                | Mixed-Use Development Activity Center (must be in a Master Plan Area Boundary) |
| PD-X                 | Planned Development (where X is the associated land use category)              |

_[Source: Orange County Planning Division](https://www.orangecountyfl.net/PlanningDevelopment/ComprehensivePlanning.aspx#.X87_PGhKj-g)_