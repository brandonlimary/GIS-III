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
four aforementioned features respectively: _median income, racial/ethnic composition, grocery
store proximities, and vacant lot density_. Through this, I was able to illustrate spatial disparities
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
lenders, investors, and developers alike (Greer, 2014; Hillier, 2003). As a result, the demand to live in these Black and Brown
neighborhoods declined and those who could afford to move did (Raleigh and Galster, 2015). Today, many West and South
Side community areas still display symptoms of this racial redlining. Moreover, the degenerative
effects of this racialized redlining and municipal disinvestment can be observed by the
concentration of dilapidated housing infrastructure, vacant lots, and limited food access. Thus,
South Side community areas like Washington Park have a majority Black population that faces a
multitude of environmental, social, economic, and health challenges.

### Data plan and definitions:
Regarding data, most of my data has already been collected from my prior GIS
assignment. The data for the four variables I’m investigating (median income, racial/ethnic
composition, vacant lot density, and grocery store density) can be obtained through the Chicago
Open Data Portal and 2020 US Census/American Community Survey Data. However, since
some of the data may have changed since March, I will use API URLs where possible to pull the most
up-to-date data into my project. 

## Data Sources, Spatial and Temporal Scale

Below I define my four variables and their respective source:
  1. Income: Median household income by census tract, 2020
    . From US Census 2020, extracted from [NHGIS Data Finder](https://data2.nhgis.org/downloads)
  2. Racial composition: % non-Hispanic Black, 2020
    . From US Census 2020, extracted from [NHGIS Data Finder](https://data2.nhgis.org/downloads))
  3. Vacant lot density: City-owned land inventory, 2020
    . [From Chicago Data Portal](https://data.cityofchicago.org/Community-Economic-Development/City-Owned-Land-Inventory/aksk-kvfp)
  4. Grocery store density: Grocery stores, 2013
    . [From Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Grocery-Store-Status/3e26-zek2)
  5. Census tract shapefile, 2020
    . [From NHGIS Data Finder](https://data2.nhgis.org/downloads)
  6. Community area boundaries, present
    . [From Chicago Data Portal](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6)
  7. Chicago Property Parcels, 20210
    . [From GeoDa Center](https://geodacenter.github.io/data-and-lab/parcels/)
    
## Methods Used (be explicit)
For this project, my process can be broken into two parts: data wrangling and data visualization.

### Data Wrangling
I primarily wrangled my data using RStudio. Each variable has its method listed below. 

#### Median Income
For median income, I first loaded the data into R (I downloaded the data onto my local machine) as a CSV file. The data was in the form of a CSV. Since the data from NHGIS includes data from all 50 states, I had to first filter my data to only include data from census tracts in Cook County. Luckily, through the NHGIS documentation, I found the COUNTYA column which lists out a unique numerical code. The numerical code for Cook County is 31. After filtering out all NULL values, I saved the cleaned data to my local machine.

#### Racial Composition
For racial composition, I first loaded the data from NHGIS into R (I downloaded the data onto my local machine). The data was in the form of a CSV. Similar to the median income data, I had to filter the data by the Cook County area code. 

#### Vacant Lot Density
For vacant lot density, I first loaded the data into R (I downloaded the data through the Chicago Data Portal SODA API). I then resaved the data as a shapefile.

#### Grocery Store Density
For grocery store density, I first loaded the data into R (I downloaded the data through the Chicago Data Portal SODA API). The data was in the form of a CSV file with location data stored in a column titled 'Location'. I resaved the data as a shapefile.

### Data Visualizations
To visualize the data, I loaded my cleaned data into QGIS as CSVs and shapefiles. Each variable had its own stylizing layer in QGIS. The basemap, census tract shapefile, and community area boundaries were also loaded in as separate layers. I joined the Median Income and Racial Composition datai QGIS to the census tract shapefile using the GISJOIN field. The Vacant Lot Density and Grocery Store Density data was loaded in QGIS as shapefiles and I used QGIS's spatial join function to join the vacant lot point data. 

For the racial composition layer, I decided to use rule-based styling methods to showcase each race as a point. For the vacant lot data, I decided to represent the points as polygons based on Chicago parcels polygons using a spatial join. This allowed for a visualization of the actual lots that were vacant, not just where they were located. Unfortunately, the spatial join for the vacant lots was not perfect and, despite troubleshooting, I was only able to spatially join the vacant lots to the parcel polygons for some areas of the extent.

To save my maps, I used the QGIS map layout function to create PNGs of the maps at the same spatial extent. Legends were added at the part of the stage.

## Results

### Median Income
![Median Income](https://user-images.githubusercontent.com/74623945/170792854-551ae605-3314-45c0-8bc5-7333ca6f2aec.png)

### Race
![Race](https://user-images.githubusercontent.com/74623945/170792866-433193b9-f661-4d53-b808-3408f67fdf36.png)

### Grocery Stores
![Grocery Stores](https://user-images.githubusercontent.com/74623945/170792880-0b95a04c-5f2a-44c1-a46d-d660420031ed.png)

### Vacant Lots
![Vacant Lots](https://user-images.githubusercontent.com/74623945/170792888-4be7ac4a-fcef-4be3-8ab9-1a2006210e4b.png)

## Discussion of Results/Findings/Main Highlights
The series of maps provided above highlight the importance of a multi-disciplinary approach when constructing spatial models. While the four variables I chose to investigate for this project are by no means meant to serve as a comprehensive mosaic that captures Washington Park as a community area. Rather, these four variables serve as a preliminary conceptual model to describe key features of Washington Park. As observed from the maps, while there exists some spatial differentiation outside of the Washington Park community area, the maps show how the variables of investigation characterized the entirety of Washington Park consistently. The lack of grocery stores and high density of vacant lots alongside census tracts with median incomes in the first quartile and an almost entirely Black population, show a glimpse into the character of disinvestment and racialized discrimination that has occurred in the area. Especially when compared to neighboring communities, especially Hyde Park, one truly sees how stark Washington Park stands out.

## Limitations, Future Work, Conclusion
Despite utilizing the most up-to-date data, the accuracy of the data itself will not be 100% aligned with reality. Human error and inconsistences in data collection, anonymization techniques by the US. Census Bureau, and inaccurate self-reported information are all factors that may introduce erroneous data. However, the scale at which my analysis occurs allows for general spatial patterns, distributions, and analyses to be made soundly.

Moreover, further work should work to make the maps interactive (perhaps through an RShiny application!) and accessible online. This would greatly increase the audience and impact of my work and more deeply engage community stakeholders with the most up-to-date information. 

On a final note, this process seeks to highlight the relevance and capacity for GIS to derive insights for communities. At each step, both in data wrangling and visualization, there is an opportunity to derive insights about the community character, both within and outside its boundaries, to better understand its needs, assets, and areas for potential growth. The importance of leveraging green space, for example, in the community cannot be understated, given how such land could be used for community meeting sites, educational and career development locations, and other spaces for growth that the community may need. Of course, it is of utmost importance for the community and its stakeholders to be involved in the development of its area; this project merely seeks to serve as a stepping stone toward more community-led conversations and as a tool for aspiring organizers and activists within the community. This project stands as an evolution to prior work done by me, with the data new accessible online and with the maps viewable in a side-by-side layout.

## References
Greer, J. L. (2014). Historic Home Mortgage Redlining in Chicago. Journal of the Illinois State Historical Society (1998-), 107(2), 204–233. https://doi.org/10.5406/jillistathistsoc.107.2.0204

Hillier, A. E. (2003). Spatial analysis of historical redlining: a methodological exploration. Journal of Housing Research, 137-167.

Raleigh, E., & Galster, G. (2015). Neighborhood Disinvestment, Abandonment, and Crime Dynamics. Journal of Urban Affairs, 37(4), 367–396. https://doi.org/10.1111/juaf.12102
