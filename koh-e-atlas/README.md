## Koh-e-Atlas Karachi

[Karachi](https://en.wikipedia.org/wiki/Karachi), despite being the 13th most populous city globally, suffers from a severe lack of open-source spatial data, hindering informed policy-making and the visibility of urban challenges, particularly in marginalized areas. Therefore, this project aims to create an open-access atlas of thematic maps for [Karachi](https://en.wikipedia.org/wiki/Karachi), documenting various data such as administrative boundaries and mobility. The purpose is to inform policy-making and raise awareness about open-source data and mapping.

### Methodology

#### Socio-economic Indicator

1. Tehsil Boundaries Karachi:
The updated Town or Tehsil boundaries have been manually created using the images of the 2017 updated town boundaries available on the Urban Resource Centre website. The snapping tool on QGIS was used to create the shapefiles of all the towns and cantonments of Karachi.

2. Population Density of Karachi:
The map is created using population estimates of Pakistan for 2018 by WorldPop. Karachi was divided into a 1by1 Km grid using tools on QGIS. Then raster data from Worldpop was converted into a point vector and the sum of all points in each grid was calculated. The resultant shapefile contains 3936 1by1 km grids of Karachi with population. The heat map was created to show the spatial inequality in the density of the city.

3. Karachi Towns Population Growth Rate:
Using the shapefiles created above and Census 2017 data available on the Pakistan Bureau of Statistics website, town town-level population growth map of Karachi was created. After calculating the growth rate of 20 years from 1998-2017, a simple join was applied to link the data with the shapefiles. A heat map was created to show the spatial inequality in the growth of the population.

4. Karachi Literacy and Languages:
Using the shapefiles of Karachi towns created for this project and literacy and language data from the Population Census 2017, categorical maps were created to represent the spatial inequality in literacy and the diversity in Karachi. The simple join was used to integrate the census data into QGIS.

5. Shrines of Karachi and Parsi Heritage Sights:
These maps were created based on secondary research on the shrines in Karachi and spaces that are being used by the Parsi community in the city. Using Google maps, lot/long were mapped and then the QGIS plugin qgis2web was used to create these web maps.

#### Urban Planning and Climate Change:

1. Electricity Consumption and Losses in Karachi:
Using open data available on Karachi electricity losses by K-electric, this map has been created in QGIS with the help of a spatial join. Heat maps are created to show the spatial variation in electricity losses and consumption per capita in the city.

2. Pedestrian Bridges in Karachi:
The data for this map comes from the research of Sajjad Mehdi, a journalist at Aaj News. Primary and Secondary road data for Karachi comes from Open Street Maps which has been merged to create a single layer. This map represents the unequal distribution of pedestrian bridges in Karachi.

3. Urban Sprawl in Karachi:
This map has been created using satellite imagery of Karachi on Google Earth Pro. Shapefile was created for the three years 2004, 2014, and 2024 and then exported to QGIS. The map shows the expansion of urban built-up in Karachi over the years.

4. Lyari Expressway Displacement:
This map was also created using satellite imagery of Karachi. The communities that have been removed since 2001 were mapped creating shapefiles on Google Earth Pro which were then exported to QGIS for further analysis.

5. Mangroves Loss in Machar Colony:
Similar to the above two maps, this map has been created using the timeline feature of Google Earth Pro. Shapefiles of mangroves were created for 2001 and 2024 to capture how much area of mangrove forest has been lost. Analyses on QGIs showed that this area amounts to a total of 14 cricket grounds.

6. Major Water Channels and Nullahs of Karachi:
This map has been created using a combination of secondary research, satellite imagery, and available data on OSM. Vector lines of nullahs were created in QGIS to represent the waterways in Karachi.

7. Katchi Abadis in Karachi:
These maps were created using Google Earth Pro and the Mapflow plugin in QGIS. The shapefiles for the abadis were created using satellite imagery and then the mapflow plugin was used to detect the buildings and green cover in them. The health facilities were mapped using Open Street Maps

#### Transportation

These maps were created with the help of primary research. Routes were tracked with the help of My Track App while riding the buses and main bus stops were recorded using the Kobo Toolbox Survey. Data was cleaned and layouts were created in QGIS. A final map was created after merging all the bus routes' vector lines that were mapped in this research.

### Data Repository

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.13910955.svg)](https://doi.org/10.5281/zenodo.13910955)

### File Descriptions

The shapefiles for all the maps are available in SHP format, facilitating easy integration into any GIS software including QGIS and ArcGIS for further analysis. Each shapefile contains an attributes table for all the available data related to that vector. The data is structured to support spatial and statistical analysis, enabling researchers to further extend this research and policymakers to make informed decisions.

The dataset comprises the following zipped folders:

1. Delhi Colony.shp.zip contains shapefiles for Delhi Colony, its buildings, green cover, and medical facilities.
2. Karachi electricity.shp.zip contains shapefiles for connection details of towns and per capita consumption of towns.
3. Karachi lang & literacy data.shp.zip contains shapefile which contains town-level information for both literacy and language data from the 2017 census
4. Karachi manzoor colony.shp.zip contains shapefiles for Manzoor Colony, its buildings, green cover, and medical facilities
5. Karachi Parsi Heritage.shp.zip contains Parsi heritage sites shapefile
6. Karachi Pedestrian bridges.shp.zip contains the shapefiles of the pedestrian bridges, primary and secondary roads of Karachi, and the original Excel sheet from Sajjad Mehdi
7. Karachi Shrines.shp.zip contains the shapefile of the shrines in Karachi
8. Karachi Towns Population Growth Rate.shp.zip contains the shapefile of the town-wise population growth rate of the city
9. Karachi Towns.shp.zip contains the shapefiles of all the towns and cantonments of the city
10. Karachi waterways.shp.zip contains the shapefile of all the mapped waterways of the city
11. KHI_Popden.shp.zip contains the shapefiles of the 1 by 1 km grid with its population as well as point shapefile for Mazar e Quaid
12. Koh-e-Atlas Bus routes.shp.zip contains the bus routes shapefiles that were mapped during this research
13. Lyari Expressway.shp.zip contains the shapefiles of the expressway and the communities that have been removed
14. Mangroves Machar Colony.shp.zip contains the mangroves shapefiles that remain and that have been lost
15. Pelhwan Goth.shp.zip contains shapefiles for Manzoor Colony, its buildings, green cover, and medical facilities
16. Surjani Town.shp.zip contains shapefiles of the built up in Surjani town in 2004, 2014, and 2024 and of Surjani town as well.

### Data Summary

The data files contain over 55 shapefiles on socio-economic indicators, climate and urban factors, and bus routes of Karachi. Cleaning and Preliminary analysis has been done for all shapefiles. These shapefiles can be used for further extension of the same work, provide a baseline for future research, and inform policy makers working for the relevant issues.

### Status

The project has completed and data is available for download.

### License

The data is available under the [Creative Commons Attribution Non Commercial 4.0 International](https://creativecommons.org/licenses/by-nc/4.0/legalcode) license.

### Cite as

```bibtex
@dataset{makati_2024_13910955,
  author       = {Makati, Zaineb},
  title        = {Koh-e-Atlas Karachi},
  month        = oct,
  year         = 2024,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.13910955},
  url          = {https://doi.org/10.5281/zenodo.13910955}
}
```

### Team Members

#### Principal Investigator

- Zaineb Makati (Supervisor)
- Aatika Saleem (Co-supervisor)

#### Student Researchers

- Muhammad Khubaib Mukaddam
- Mehlab Kashani
- Daniyal Shadab

#### External Collaborator

- Saniyal Saleem

### Acknowledgements

- Habib University Deans Fellowship Grant
- Habib University Summer Tehqiq Research Grant

Go to: [Top](#koh-e-atlas-karachi) | [Data Research Lab - Pakistan](https://darlab-pakistan.github.io/)
