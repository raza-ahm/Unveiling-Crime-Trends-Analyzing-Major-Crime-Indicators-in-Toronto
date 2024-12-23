# Unveiling Crime Trends: Analyzing Major Crime Indicators in Toronto

<div align="center"> <h2>Introduction<h2> </div>

### Purpose
The goal of this project is to educate Torontonians about crime in their neighborhoods using the Toronto Police Service's Major Crime Indicators Open Dataset. By presenting the data in a simple and accessible way, I aim to spark discussions on public safety and help residents make informed decisions.

### Methodology
The analysis will be conducted primarily using the Python programming language. Python will be utilized for preprocessing, cleaning, exploring, and analyzing the dataset, providing comprehensive insights throughout the process. The steps involved in this analysis will be documented and executed within Jupyter notebooks, ensuring a clear and detailed breakdown of each phase.

Upon completion of the analysis, a Tableau dashboard will be created and shared. This dashboard will offer users an interactive platform to explore the dataset further, enabling deeper insights and engagement with the data. 

### Overview of the Dataset
#### Link to original dataset: https://data.torontopolice.on.ca/datasets/TorontoPS::major-crime-indicators-open-data/about

#### Source: 
This dataset was published by the Toronto Police Service through their Public Safety Data Portal, which provides public access to police datasets.

Some data may be excluded for legal, privacy, security, and confidentiality reasons. Additionally, all geographic data is adjusted to the nearest road intersection to protect privacy, so the locations are approximate and not tied to specific addresses or individuals. 

#### Description:
This dataset records occurrences of Major Crime Indicators (MCI) by reported date and related offenses. The MCI categories include Assault, Break and Enter, Auto Theft, Robbery, and Theft Over $5000 CAD (excluding Auto Theft). It does not include incidents that were deemed unfounded or did not occur after police investigation.

Even though the dataset includes incidents that occurred before the year 2000, I am removing those incidents. My reasoning is that analyzing 24 years of incidents (2000 - 2024) is more than sufficient for educating everyday Torontonians in a simple and accessible manner about the nature of various crimes occurring in their neighborhoods. This period provides a substantial and relevant dataset that captures recent trends and patterns in crime, ensuring the analysis remains current and useful for community discussions and safety measures.

As of the time of writing, the dataset includes MCI records up to the third quarter of 2024.


### 1) Data Preprocessing and Cleaning:




