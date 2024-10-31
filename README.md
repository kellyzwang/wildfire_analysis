# Wildfire analysis

### Project Goal

This repository contains all code and resources for analyzing wildfire impacts in Chico, CA. The end goal is to be able to inform policy makers, city managers, city councils, or other civic institutions, to make an informed plan for how they could or whether they should make plans to mitigate future impacts from wildfires.


### Directory Structure

```
├── common_analysis
|   └── data
|   └────── fire_data_checkpoint.csv
|   └────── gaseous_pollutants_data.csv
|   └────── particulate_pollutants_data.csv
|   └── wildfire
|   └────── Reader.py
|   └────── ...
|   └── aqi_data.ipynb
|   └── wild_fire_data.ipynb
|   └── common_analysis.ipynb
|   └── figure_descriptions_and_reflection.pdf
├── LICENSE
├── README.md
```

### Data Sources
- The **wildfire data** is retrieved from the [combined wildland fire datasets for the United States and certain territories, 1800s-Present (combined wildland fire polygons)](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) dataset collected and aggregated by the US Geological Survey.  The dataset provides fire polygons in ArcGIS and GeoJSON formats. The `USGS_Wildland_Fire_Combined_Dataset.json` file is used in our data acquisition process.

- The **Air Quality Index (AQI) data** is retrieved using the [US EPA Air Quality System (AQS) API](https://aqs.epa.gov/aqsweb/documents/data_api.html).

### To Reproduce the Analysis

#### Part 1 - Common Analysis

In part 1, we conduct a base analysis to answer the common research question: What are the estimated wildfire smoke impacts on your assigned city each year for the most recent 60 years of wildfire data?

 * The `aqi_data.ipynb` notebook contains code to collect and pre-process daily AQI data from the API. The collected AQI data is saved as `gaseous_pollutants_data.csv` and `particulate_pollutants_data.csv` in the data folder. Later, the gaseous and particulate pollutants data are combined in the analysis step to calculate the average AQI, which is then aggregated to a yearly level.

 * The `wild_fire_data.ipynb` notebook contains code to collect and pre-process wildfire data. The collected wildfire data is saved as `fire_data_checkpoint.csv` in the data folder. This data file contains the fire year (`Fire_Year`), fire name (`Fire_Name`), fire size (`GIS_Acres`), fire type (`Fire_Type`), and distance to Chico (`Distance`), used to calculate the smoke estimates.

 * The `common_analysis.ipynb` notebook contains code to create fire smoke estimates in Chico, produce visualizations, and predicts smoke estimates for every year for the next 25 years (2025-2050).



 ### License
 - Example code to [access the US EPA Air Quality System (AQS) API](https://drive.google.com/file/d/1fwS60QStiMDqwINvW2LEDFBX5xg6Wnmg/view?usp=drive_link) and to [compute the geodetic distance](https://drive.google.com/file/d/1B7AGlaW7d-27bHKLVXGBwLt8T-Elx-HB/view?usp=drive_link) between all of the fires and Chico, CA were referenced. These code examples were developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the [Creative Commons](https://creativecommons.org/) [CC-BY license](https://creativecommons.org/licenses/by/4.0/).
 - The code in this repository is available under the [MIT license](https://opensource.org/license/mit).
