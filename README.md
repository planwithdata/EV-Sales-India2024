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

Make sure to read the comments at the top of the scripts for directions on how to run. Most reuire a single or no file to run. 

Thankyou!

