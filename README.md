# GIS-III Final Project
by Brandon Limary

## Goals and Objectives, Research Question

The overall goal for this project is to expand on a prior project I undertook in GIS II
which worked to generate a conceptual model of the Washington Park community area in
Chicago. In the prior project, I was able to develop a conceptual spatial model of Washington
Park that considered four distinguishing features: low-income residents, racial
homogeneity/strong black majority, municipal disinvestment, and an abundance of green space
due to the park and prevalence of vacant lots. The objectives put forth to achieve this goal
involved the extraction, transformation, and loading of four variables of interest related to the
four aforementioned features respectively: median income, racial/ethnic composition, grocery
store proximities, and vacant lot density. Through this, I was able to illustrate spatial disparities
and characteristics of the Washington Park community area via social, economic, and
infrastructural lenses. However, the final product of my research was a series of maps not easily
readable nor aesthetic for general public audiences. Given the scope and implications of this
research, I hope to synthesize the data from my prior research and generate a visually appealing
and readable map that is accessible online. Thus through the direct objectives of incorporating
high-quality design and cartographic principles, utilizing advanced web visualizations, and
making my code open-source and accessible, I can achieve the goal of expanding upon my prior
research toward a more accessible product.

## Background, Motivation

As many Chicagoans and outsiders know, Chicago is one of the most racially/ethnically
segregated cities in the US. Since the Great Migration, Chicago's West and South Sides have
been torn by redlining, racial segregation, predatory lending practices, and disinvestment by the
city. Decades of race-based discrimination made the South and West Sides unattractive to
lenders, investors, and developers alike. As a result, the demand to live in these Black and Brown
neighborhoods declined and those who could afford to move did. Today, many West and South
Side community areas still display symptoms of this racial redlining. Moreover, the degenerative
effects of this racialized redlining and municipal disinvestment can be observed by the
concentration of dilapidated housing infrastructure, vacant lots, and limited food access. Thus,
South Side community areas like Washington Park have a majority Black population that faces a
multitude of environmental, social, economic, and health challenges.
Data plan and definitions:
Regarding data, most of my data has already been collected from my prior GIS
assignment. The data for the four variables I’m investigating (median income, racial/ethnic
composition, vacant lot density, and grocery store density) can be obtained through the Chicago
Open Data Portal and 2020 US Census/American Community Survey Data. However, since
some of the data may have changed since March, I will use API URLs to pull the most
up-to-date data into my project. 

## Data Sources, Spatial and Temporal Scale

Below I define my four variables and their respective source:
  1. Income: Median household income by census tract, 2020
    a. From US Census 2020, extracted from [NHGIS Data Finder]([url](https://data2.nhgis.org/downloads))
  2. Racial composition: % non-Hispanic Black, 2020
    a. From US Census 2020, extracted from [NHGIS Data Finder]([url](https://data2.nhgis.org/downloads))
  3. Vacant lot density: City-owned land inventory, 2020
    a. [From Chicago Data Portal]([url](https://data.cityofchicago.org/Community-Economic-Development/City-Owned-Land-Inventory/aksk-kvfp))
  4. Grocery store density: Grocery stores, 2013
    a. [From Chicago Data Portal]([url](https://data.cityofchicago.org/Health-Human-Services/Grocery-Store-Status/3e26-zek2))
  5. Census tract shapefile
    a. [From NHGIS Data Finder]([url](https://data2.nhgis.org/downloads))
  6. Community area boundaries
    a. [From Chicago Data Portal]([url](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6))
    
## Methods Used (be explicit)
For this project, my process can be broken into two parts: data wrangling and data visualization.

### Data Wrangling
I primarily wrangled my data using RStudio (code provided in file titled 'code'). Each variable has its method listed below.

#### Median Income
For median income, I first loaded the data into R (I downloaded the data onto my local machine). 

#### Racial Composition
For racial composition, I first loaded the data into R (I downloaded the data onto my local machine).

#### Vacant Lot Density
For vacant lot density, I first loaded the data into R (I downloaded the data through the Chicago Data Portal SODA API). 

#### Grocery Store Density
For grocery store density, I first loaded the data into R (I downloaded the data through the Chicago Data Portal SODA API). The data was in the form of a CSV file with location data stored in a column titled 'Location'. 

### Data Visualizations
To visualize the data, I loaded my cleaned data into QGIS as shapefiles. Each variable had its own stylizing layer in QGIS. The basemap, census tract shapefile, and community area boundaries were also loaded in as seperate layers.

## Results (if a Dashboard, insert screenshots of key selections)

### Median Income
![Median Income](https://user-images.githubusercontent.com/74623945/170792854-551ae605-3314-45c0-8bc5-7333ca6f2aec.png)

### Race
![Race](https://user-images.githubusercontent.com/74623945/170792866-433193b9-f661-4d53-b808-3408f67fdf36.png)

### Grocery Stores
![Grocery Stores](https://user-images.githubusercontent.com/74623945/170792880-0b95a04c-5f2a-44c1-a46d-d660420031ed.png)

### Vacant Lots
![Vacant Lots](https://user-images.githubusercontent.com/74623945/170792888-4be7ac4a-fcef-4be3-8ab9-1a2006210e4b.png)

## Discussion of Results/Findings/Main Highlights
The series of maps provided above highlight the 

## Limitations, Future Work, Conclusion
Despite utilizing the most up-to-date data, the accuracy of the data itself will not be 100% with reality. 
