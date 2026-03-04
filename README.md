# KAVI_PIT-UN_Hackathon_Data
## Overview

This dataset includes census tract-level demographic and economic information including poverty & employment status, race, age, median rent, mean income  and median home price. There are also shapefiles for NYC city boundaries, NYPD precinct boundaries, and reported shooting incidents. 

## Data Sources

*   US Census Tiger-Line Shapefiles: Secondary, Public 
	* New York State Census tract boundary shapefiles for the 2010 and 2020 decadal censuses (https://www.census.gov/cgi-bin/geo/shapefiles/index.php)
	* 2010 census tracts: tl_2010_36
	* 2020 census tracts: tl_2020_36

*   US Census Bureau: Secondary, Public
    *   All data from American Community Survey 5 year estimates for 2010, 2015, 2020, and 2024 (data.census.gov)
    	* poverty_education_employment: S1702 dataset(2010), S1701 dataset(2015-2024)
	* Demographics: DP05 dataset
	* mean_income: S1902 dataset
	* median_home_price: B25077 dataset
	* median_rent: B25058 dataset

*   NYC Open Data: secondary, public (https://data.cityofnewyork.us)
    *   Shapefiles of NYC borough and police precinct boundaries
	* borough boundaries
	* precinct boundaries
	* NYPD shooting reports from 2006-2024

## Data Processing & Cleaning

All census csv data was processed to extract tract GEOIDs and cleaned to only include relevant information identified in column headers. The only inconsistency between datasets is in the povert_education_employment datasets, where the 2010 data uses the S1702 dataset which measures by family/household rather than individual. The S1702 dataset also required an excel calculation to derive a number of families below poverty level as the original dataset only provided a percent value. 

The shootings_by_year shapefile was separated by year using ArcGIS.

Shapefiles are unmodified and will require projection into Long Island State Plane. 


## Data Structure

The data is organized as follows:

*   `Raw Data/`: This folder contains data taken from US Census
    *   `Demographics`: This folder contains raw DP05 datasets for 2010, 2015, 2020, and 2024
    *   `mean_income`: This folder contains raw S1902 datasets for 2010, 2015, 2020, and 2024
    *   `medain_home_price`: This folder contains raw B25077 datasets for 2010, 2015, 2020, and 2024
    *   `median_rent`: This folder contains raw B25058 datasets for 2010, 2015, 2020, and 2024
    *   `poverty_education_employment`: This folder contains raw S1701 datasets for 2015, 2020, and 2024 and the raw S1702 dataset for 2010 
   
   

*   `Cleaned Data/`: This folder contains cleaned Census data.
    *   `Demographics`: This folder contains cleaned DP05 datasets for 2010, 2015, 2020, and 2024
    *   `mean_income`: This folder contains cleaned S1902 datasets for 2010, 2015, 2020, and 2024
    *   `medain_home_price`: This folder contains cleaned B25077 datasets for 2010, 2015, 2020, and 2024
    *   `median_rent`: This folder contains cleaned B25058 datasets for 2010, 2015, 2020, and 2024
    *   `poverty_education_employment`: This folder contains cleaned S1701 datasets for 2015, 2020, and 2024 and the cleaned S1702 dataset for 2010 
   

*   `Shapefiles/`: This folder contains shapefiles.
    *   `shooting_by_year/`: This folder contains point layers for reported shootings for every year from 2006-2024
    *   `geo_export_37d62e41-f327-4358-a2f8-ad2185e6e10a.shp`: raw shooting data
    *   `nybb`: boundaries of NYC boroughs
    *   `NYC_Precinct_Boundaries`: NYPD precinct boundaries
    *   `tl_2010_36`: 2010 census tracts
    *   `tl_2020_36`: 2020 census tracts





## Use Cases and Inspiration

*   Look into how the number of shooting in a given area changed after the establishment of a local CMS organization.
*   Create a dashboard that allows for users to easily access contact information for CMS organizations.
*   Make the dashboard able to easily incorporate shooting and demographic data in future years
