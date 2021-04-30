# NYC-MTA: Who got to stay home?
Diego Wahl

# Abstract
The idea for this project began with the question as to whether there is a clear and obvious relationship between the wealth/income of a neighborhood/zip code, and changes in MTA ridership of that area during the Covid-19 pandemic. In order to do so, I would be required to follow a data lineage as follows: MTA Station -> Zip Code -> Median Income. The latter two of which are not included in the data MTA freely provides. Given that, generally, higher-paying jobs tend to be those that would allow the freedom to work from home (i.e., “non-essential” work), one could posit that there would be a correlation between a zip code’s median income and a decrease in ridership during the pandemic.

# Design
This analysis sought to breakdown changes in MTA ridership as a function of the station's zip code's median income. A baseline of ridership was created with MTA data from 2019 centered on the month of May (as well as some data from both late April and early June) and used in comparison with those same dates in the year of 2020, after the Covid-19 pandemic had begun. 

# Data
As previously mentioned, the core of this project required pulling from a number of data sources in order to form a cohesive view of ridership changes in relation to income. After loading the relevant MTA data (consisting of the months of April, May and June of 2019 and 2020) into a SQL database, Google Maps API were used in order to programmatically identify the zip code for each distinct MTA station. Median ncome data were obtained from the data.census.gov website at the zip code level for the NYC-area. Similarly to the MTA data, station to zip code mappings, as well as the zip code to median income mappings received their own SQL tables for easy access and retrieval. 

# Algorithms
Data was cleaned via removal incongruent data (such as removal of data that would imply an unreasonable level of ridership) and removal of duplicate data. In some cases outliers (such as the cases in which a station saw a positive change in ridership between the two sets of MTA data date ranges) were removed for the benefit of visualization and calculation of correlation between variables. MTA stations were matched to their relevant Zip Codes and median income through simple table joins, and data was aggregated and manipulated in both SQL and Pandas DataFrames.

# Tools
* googlemaps, json, and urllib Python packages were used to handle the Google Maps API requests and subsequently manipulate responses.
* SQL database via SQLite3 was used for data storage, manipulation, and retrieval.
* Sqlalchemy interfaced the SQL database to Python.
* Pandas package in Python employed for data cleaning and manipulation.
* Lastly, Matplotlib and Seaborn used for visualization.


# Communication
Findings were shared with Metis Data Science cohort in addition to being posted on github. Matplotlib and Seaborn were used for visualization.

![Screenshot 2021-04-29 at 5 15 03 PM](https://user-images.githubusercontent.com/29666424/116699545-4ea64580-a98b-11eb-8349-667bf39b5e0e.png)
![IncvRide no Pos](https://user-images.githubusercontent.com/29666424/116699552-51089f80-a98b-11eb-91ef-ba83b7f0313a.png)
![IncvRide w Pos](https://user-images.githubusercontent.com/29666424/116699558-52d26300-a98b-11eb-82f7-c08f7c166673.png)
