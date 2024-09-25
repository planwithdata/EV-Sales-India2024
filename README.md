# EV Sales and Charging Infrastructure Analysis (Delhi)

## Project Overview
This project focuses on analyzing the electric vehicle (EV) market, specifically electric 2- and 3-wheelers (e2/3W), and their supporting charging infrastructure in Delhi. The aim is to evaluate sales growth, the distribution of charging stations, the relationship between EV sales and charging infrastructure, and gain spatio-temporal insights into these factors. The analysis focuses on both charging stations and battery swapping stations, rated for slow AC charging (<3-4 kW).

## Key Components

### 1. Web Scraping: EV Sales and Charging Infrastructure
- **Objective:** Extract historical EV sales data for e2/3W in Delhi over the past five years and identify the top 5 models and manufacturers based on cumulative sales or market share.
- **Charging Stations:** Scrape detailed information about charging and battery swapping stations, including their locations (latitude/longitude), number of charging points, payment options, and the top companies by market share in terms of installations.
- **Deliverables:** Code and scripts for web scraping, along with an Excel file containing historical sales and charging infrastructure data.

### 2. Regression Modeling: EV Cost and Specifications
- **Objective:** Web scrape detailed vehicle specifications for electric three-wheeler autos (L5M category) and develop a multiple linear regression (MLR) model to analyze the relationship between vehicle specifications and cost.
- **Top Diesel/CNG L5M Comparison:** Compare the top-selling diesel or CNG three-wheeler (L5M) with its closest electric equivalent based on vehicle specifications.
- **Deliverables:** Code/scripts for web scraping, a clean dataset of vehicle specifications, regression model output, diagnostic plots, and insights into the model's predictive power and key relationships.

### 3. Spatial Analysis: EV Sales and Charging Infrastructure in Delhi
- **Objective:** Plot the cumulative e2W and e3W sales across Delhi using district shapefiles, overlayed with Regional Transport Offices (RTOs), charging stations, battery swapping stations, and Points of Interest (PoI) such as malls, metro stations, and more.
- **Deliverables:** GIS files in formats such as GeoPackage, shapefiles, or GeoJSON, along with spatial visualizations including cluster maps and heatmaps to identify areas lacking charging infrastructure.

### 4. Exploratory Data Analysis and Reporting
- **Objective:** Analyze the spatial relationship between e2/3W sales and the distribution of charging and swapping stations, using methods like clustering and proximity analysis. Further insights will be drawn from PoI data and its relationship with EV sales and infrastructure.
- **Deliverables:** A write-up summarizing the key insights, including trends and spatial analysis outputs such as maps, clusters, and heatmaps.

## Technologies Used
- **Web Scraping:** Python (BeautifulSoup, Selenium)
- **GIS:** QGIS, GeoPandas, and custom Python scripts
- **Data Analysis and Visualization:** Pandas, Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn for regression modeling

## Project Structure
|-- data/ # Collected datasets (EV sales, charging stations, vehicle specs) |-- scripts/ # Web scraping and analysis scripts |-- output/ # Visualizations, regression model outputs, spatial analysis results |-- README.md # This file |-- LICENSE # License for the project


## How to Run the Project
1. Clone the repository.
2. Run the scraping scripts under `scripts/` to gather the required data.
3. Use the spatial analysis scripts to generate visualizations for GIS-related tasks.
4. Run the regression model and EDA notebooks to analyze the relationship between vehicle specs and cost, and examine the relationship between EV sales and charging infrastructure.

## Conclusion
This project provides an in-depth look at the electric 2- and 3-wheeler market in Delhi and the corresponding infrastructure that supports it. The insights gained from this analysis will help identify the growth trends and gaps in infrastructure, guiding further deployment of EV charging stations.

# Key Results and Responses

## Assignment 1:

### EV Sales (Vendor)
![EV Sales Output](https://github.com/planwithdata/EV-Sales-India2024/blob/main/Data/Screenshots/EV_sales_output.png)

### Charging Stations and Battery Swapping Stations
![Charging Stations Map](https://github.com/planwithdata/EV-Sales-India2024/blob/main/Data/Screenshots/Future%20EV%20Sales%20Prediction.png)

### Answer: Charging Infrastructure in Delhi

We can see observations clearly upon observing the map:
- There are fewer charging stations/battery swapping stations in West Delhi and North Delhi compared to other parts.
- These areas have residential zones, and hence EV sales could increase in these regions in the future.
- Upon checking with Land use and overlaying the residential layer, it shows that the charging stations have been installed in the close vicinity of residential areas but not in residential areas themselves. They are situated near points of interest and high population areas.
- While EVs can serve as a good alternative to Metros, we observe many charging stations installed near Metro routes. Hence, EV sales could penetrate areas where metro connectivity is limited.
- Some charging stations are installed in lines, suggesting that they are located along main roads at intervals.

## Assignment 2:

- Imported data from 4 websites. Finalized 100 observations for the Multiple Linear Regression (MLR). Data still needs further processing for better analysis.

### MLR Summary:

- Answer: While the data from the websites still requires significant post-processing, the regression analysis shows useful results. We observe expected signs in most variables, though some deviations exist. The R-squared value is relatively low, indicating that the selected variables do not fully explain the relationship with EV prices. Future improvements could include searching for a broader spectrum of variables and cleaning the data more effectively.

- Among the variables analyzed, Max Speed, Power, Kerb Weight, and Width showed a strong relationship with Price. Future predictions can be made when data that demonstrates statistical significance is available.

## Assignment 3:

Collected and mapped POI, RTOs, prospective EV sales locations as a heatmap, and performed a final spatial and exploratory analysis on Delhi to investigate charging infrastructure and EV sales.

[Open Delhi Sub-District EV Sales Distribution Map](https://github.com/planwithdata/EV-Sales-India2024/blob/main/Data/Screenshots/EV_sales_POI_RTOs_map_corrected.html)

### Reasoning for EV Sales Distribution:

This analysis estimates and distributes EV sales across Delhi sub-districts using residential land use and population data as proxies. Here’s how the process works:

1. **Spatial Join of Residential Land Use and Sub-District Boundaries:**
   A spatial join is performed between residential land use polygons and sub-district boundaries to determine which residential areas fall within each sub-district.

2. **Calculate Residential Area:**
   The residential area within each sub-district is calculated, representing potential EV buyers.

3. **Sum Residential Area for Each Sub-District:**
   Total residential area is aggregated within sub-districts, providing an estimate of residential capacity.

4. **Population Weight Calculation:**
   Population data is used to calculate a weight that reflects demand for EVs in each sub-district.

5. **Combining Population and Residential Area Weights:**
   A combined factor reflecting both population size and residential land use is used to distribute EV sales across sub-districts.

6. **EV Sales Distribution:**
   Total EV sales (200,000 in this case) are distributed proportionally across sub-districts based on the combined factor.

7. **Visualization of EV Sales:**
   A map visualizes the EV sales distribution, with darker shades representing higher estimated sales.

### Key Assumptions:
- **Population size** correlates with potential EV buyers.
- **Residential land use** is an indicator of where EV sales might occur.
- The combination of population size and residential land use helps distribute EV sales in the absence of detailed sales data.

## Exploratory Data Analysis and Reporting [DELHI]

- Fewer charging stations are located directly in residential areas, though many are situated nearby.
- Notable areas like Delhi Cantonment and Mahipalpur have fewer charging stations, despite being central locations.
- The expansion of charging stations in the last 2-3 years has rapidly increased Delhi’s readiness to adopt EVs.
- Proximity analysis shows that West Delhi and North Delhi are underdeveloped in terms of charging infrastructure and could be the next regions for growth.
- Future analysis, utilizing detailed on-road data, could further refine the accessibility of charging stations.


![Future EV Sale Regions] (https://github.com/planwithdata/EV-Sales-India2024/blob/main/Data/Screenshots/FutureEVSalesPrediction.png)

Make sure to read the comments at the top of the scripts for directions on how to run. Most require a single or no file to run. 

Thankyou!

