# Unveiling Crime Trends: Analyzing Major Crime Indicators in Toronto

## Purpose
The goal of this project is to educate Torontonians about crime in their neighborhoods using the Toronto Police Service's Major Crime Indicators Open Dataset. By presenting the data exploratory and insights process in a simple and accessible way, I aim to spark discussions on public safety and help residents make informed decisions.

## Methodology
The analysis will be conducted primarily using the Python programming language. Python will be utilized for preprocessing, cleaning, exploring, and analyzing the dataset, providing comprehensive insights throughout the process. The steps involved in this analysis will be documented and executed within Jupyter notebooks, ensuring a clear and detailed breakdown of each phase.

Upon completion of the analysis, a Tableau dashboard will be created and shared. This dashboard will offer users an interactive platform to explore the dataset further, enabling deeper insights and engagement with the data. 

## Overview of the Dataset
### Link to original dataset: https://data.torontopolice.on.ca/datasets/TorontoPS::major-crime-indicators-open-data/about

### Source: 
This dataset was published by the Toronto Police Service through their Public Safety Data Portal, which provides public access to police datasets.

Some data may be excluded for legal, privacy, security, and confidentiality reasons. Additionally, all geographic data is adjusted to the nearest road intersection to protect privacy, so the locations are approximate and not tied to specific addresses or individuals. 

### Description:
This dataset records occurrences of Major Crime Indicators (MCI) by reported date and related offenses. The MCI categories include Assault, Break and Enter, Auto Theft, Robbery, and Theft Over $5000 CAD (excluding Auto Theft). It does not include incidents that were deemed unfounded or did not occur after police investigation.

Even though the dataset includes incidents that occurred before the year 2000, I am removing those incidents. My reasoning is that analyzing 24 years of incidents (2000 - 2024) is more than sufficient for educating everyday Torontonians in a simple and accessible manner about the nature of various crimes occurring in their neighborhoods. This period provides a substantial and relevant dataset that captures recent trends and patterns in crime, ensuring the analysis remains current and useful for community discussions and safety measures.

As of the time of writing, the dataset includes MCI records up to the third quarter of 2024.


## 1) Data Preprocessing and Cleaning

During the preprocessing and cleaning phase, the following adjustments were made to prepare the dataset for analysis:

**1) Column Adjustments:**

- Removed irrelevant columns, such as OBJECTID, UCR_CODE, UCR_EXT, HOOD_140, NEIGHBOURHOOD_140, and projected coordinate system columns (x, y).
- Standardized geographic identifiers by removing old neighborhood identifiers and retaining WGS84 coordinate columns for visualization.
  
**2) Data Type Conversions:**

- Converted date columns (REPORT_DATE, OCC_DATE) to date formats.
- Changed several columns to appropriate data types, e.g., categorical (REPORT_MONTH, REPORT_DOW, etc.) and integer (OCC_YEAR, OCC_DAY, etc.), to optimize performance.

**3) Handling Missing and Incorrect Values:**

- Removed rows with null values in key columns (e.g., OCC_DATE) after determining they represented outdated incidents (pre-2000).
- Retained rows with "NSA" placeholders (indicating incidents near Toronto's borders) for relevant geographic analyses.
- Updated all instances of Division 54 (D54) to Division 55 (D55) to reflect the consolidation of divisions, adjusting corresponding null values in AREA_SQKM.
  
**4) Dataset Integration:**:

- Merged the Major Crime Indicators dataset with a supplementary dataset on police divisions to include division sizes (AREA_SQKM).
- Cleaned and standardized the merged dataset for consistency.

**5) Export for Analysis:**

- The cleaned dataset was exported as Major_Crime_Indicators_Completed.csv for further analysis.

### Sample of the Cleaned Dataset

Below is a preview of the cleaned dataset after the preprocessing and cleaning steps:

| EVENT_UNIQUE_ID   | REPORT_DATE         | OCC_DATE            |   REPORT_YEAR | REPORT_MONTH   |   REPORT_DAY |   REPORT_DOY | REPORT_DOW   |   REPORT_HOUR |   OCC_YEAR | OCC_MONTH   |   OCC_DAY |   OCC_DOY | OCC_DOW   |   OCC_HOUR | DIVISION   | LOCATION_TYPE                                       | PREMISES_TYPE   | OFFENCE             | MCI_CATEGORY   |   HOOD_158 | NEIGHBOURHOOD_158            |   LONG_WGS84 |   LAT_WGS84 |   AREA_SQKM |
|:------------------|:--------------------|:--------------------|--------------:|:---------------|-------------:|-------------:|:-------------|--------------:|-----------:|:------------|----------:|----------:|:----------|-----------:|:-----------|:----------------------------------------------------|:----------------|:--------------------|:---------------|-----------:|:-----------------------------|-------------:|------------:|------------:|
| GO-20141261609    | 2014-01-01 00:00:00 | 2014-01-01 00:00:00 |          2014 | January        |            1 |            1 | Wednesday    |             9 |       2014 | January     |         1 |         1 | Wednesday |          9 | D55        | Apartment (Rooming House, Condo)                    | Apartment       | Assault             | Assault        |        069 | Blake-Jones (69)             |     -79.3381 |     43.6751 |     41.034  |
| GO-20141260033    | 2014-01-01 00:00:00 | 2013-12-31 00:00:00 |          2014 | January        |            1 |            1 | Wednesday    |             2 |       2013 | December    |        31 |       365 | Tuesday   |         22 | D42        | Single Home, House (Attach Garage, Cottage, Mobile) | House           | Assault             | Assault        |        144 | Morningside Heights (144)    |     -79.1804 |     43.8063 |     84.6117 |
| GO-20141260127    | 2014-01-01 00:00:00 | 2014-01-01 00:00:00 |          2014 | January        |            1 |            1 | Wednesday    |             1 |       2014 | January     |         1 |         1 | Wednesday |          1 | D14        | Bar / Restaurant                                    | Commercial      | Assault Bodily Harm | Assault        |        084 | Little Portugal (84)         |     -79.4271 |     43.6425 |     14.1753 |
| GO-20141260597    | 2014-01-01 00:00:00 | 2014-01-01 00:00:00 |          2014 | January        |            1 |            1 | Wednesday    |             2 |       2014 | January     |         1 |         1 | Wednesday |          2 | D14        | Apartment (Rooming House, Condo)                    | Apartment       | Assault             | Assault        |        080 | Palmerston-Little Italy (80) |     -79.4156 |     43.6549 |     14.1753 |
| GO-20141260618    | 2014-01-01 00:00:00 | 2014-01-01 00:00:00 |          2014 | January        |            1 |            1 | Wednesday    |             5 |       2014 | January     |         1 |         1 | Wednesday |          2 | D14        | Bar / Restaurant                                    | Commercial      | Assault             | Assault        |        081 | Trinity-Bellwoods (81)       |     -79.4167 |     43.6551 |     14.1753 |Bellwoods (81)       |     -79.4167 |     43.6551 |     14.1753 |

### Data Preprocessing and Cleaning Notebook

For a detailed walkthrough of the preprocessing and cleaning steps, including the Python code and commentary, refer to the [Data Preprocessing and Cleaning Jupyter Notebook](Dataset-Folder-CSV/Major_Crime_Indicators_Completed.csv.zip)
