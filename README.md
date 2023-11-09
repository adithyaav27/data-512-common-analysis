# Part 1 Common-analysis
## DATA512 Human Centered Data Science
## Goal
In recent times, the narrative of summer in the western United States has been increasingly dominated by wildfires, with plumes of smoke enveloping multiple states. Several factors are implicated in this development, including climate change, forestry management policies of the United States, and a heightened collective consciousness of such events. Irrespective of their origins, the consequences of these fires extend far and wide, affecting numerous facets of life. Studies are consistently highlighting the adverse effects of smoke on human health, tourism, property values, and the socioeconomic fabric at large.

The primary aim of this initiative is to scrutinize the repercussions of wildfire smoke on Farmington, New Mexico, with the objective of deriving actionable insights to guide diverse interested parties. Our preliminary step involves an examination of historical wildfire data to derive estimates of smoke penetration within the city's confines. Subsequently, leveraging these findings, we aim to forecast the likely smoke patterns for the forthcoming quarter-century.

## Licenses & API Information

The software code utilized for this initiative is distributed under the terms of the MIT license. For additional details, refer to the license document located in the repository's root directory. Data pertaining to Wildland Fires, provided by the USGS, are publicly available and not subject to copyright restrictions. Considering the size of the data, I have not included the file in the repository.
- Fire data: [USGS Wildfire data](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81)
- AQS API: [Air Quality System (AQS) API](https://aqs.epa.gov/aqsweb/documents/data_api.html)
- AQS API Key: Code 1.3_AQI_Data has instruction to create an account and make API calls. Please refer to that. Make sure to change the use your own USERNAME & APIKEY

## Code
There are in total of 5 notebooks that are exected to run one after the other.
If you are reading the .json file, make sure to point the directory where the data resides by changing this line found in code 1.1: C:/Users/adith/Documents/data-512-common-analysis/Data/GeoJson_Exports/USGS_Wildland_Fire_Combined_Dataset.json
- 1.1_Data_Acquisition.ipynb : Gets fire information for 1963-2020 within 1250 mile of Farmington, NM.
- 1.2_SmokeEstimateCalculation.ipynb : Ideates and creates the Smoke Estimate for 1963-2020.
- 1.3_AQI_Data.ipynb : Call the AQS API to get the Air Quality Index for Farmington and compares it with the Smoke Estimate.
- 1.4_Modelling.ipynb : Creates a predictive model of the Smoke Estimate and forcasts the estimates for the next 25 years.
- 1.5_Report_Visualizations.ipynb : Answers the Questions asked in Step 2 of common analysis Assignment on Canvas.
A dependant library class is available in /wildfire. This is imported within the notebooks.

## Inputs
- USGS_Wildland_Fire_Combined_Dataset.json
  One can bbtain this JSON file from [USGS Wildfire data](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81).
  Retrieve the 'GeoJSON Files.zip' file.
  Extract the contents of this archive into a directory of your choice. You are expected to change the directory from which this particular data is read. 
- Additional data required for the analysis will be sourced from the AQS API.

## Intermediate outputs
- aqs.csv contains the AQI data from 1963 to 2023 for air quality monitoring stations in Texerkana TX.
- distances.csv contains the wildfire data from USGS along with their calculated distance to Texarkana, TX.

Both of these intermediate files are outputs from analyze_wildfires.ipynb.

## Outputs
[Q1.png](https://github.com/adithyaav27/data-512-common-analysis/blob/main/Images/Q1.png) : This graph depicts the cumulative acreage affected by wildfires each year within a 1,250-mile radius of Farmington, NM, over the period from 1963 to 2020.
[Q2.png](https://github.com/adithyaav27/data-512-common-analysis/blob/main/Images/Q2.png) : This is a graphical representation that illustrates the spatial distribution of wildfires in relation to Farmington, NM, spanning the years 1963 to 2020.
[Q3.png](https://github.com/adithyaav27/data-512-common-analysis/blob/main/Images/Q3.png) : This is a graph illustrating the comparison between the estimated yearly smoke levels and the annual Air Quality Index (AQI) during fire seasons, spanning from 2005 to 2020.
[Step 3 Report.pdf](https://github.com/adithyaav27/data-512-common-analysis/blob/main/Step%203%20Report.pdf) This is a document containing in-depth analysis of the initial trio of diagrams presented, accompanied by a commentary reflecting on the findings.
