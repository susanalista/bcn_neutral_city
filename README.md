# PROJECT: BCN Neutral City

## *Pollution and cruise ships during high season (April to October) before and after Covid-19*

![Cruise Ship](https://3.bp.blogspot.com/-JwPjW6adyA8/TpV6iUW3MxI/AAAAAAAACtQ/nARzrLiAaNc/s1600/bcn+city+of+ships+1.10.11.jpeg)

### Data Sources:
[BCN Open Data](https://opendata-ajuntament.barcelona.cat/en)

[Statistics Department (Ajuntament de Barcelona)](https://www.bcn.cat/estadistica/angles/index.htm)

### Datasets

* Measured air pollutants by the air quality measurement stations of the city of Barcelona.
    * List of pollutants names with their codes.
* Air quality measure stations of the city of Barcelona.
    * Coordinates for location and names of neighbourhood.
* Air quality data from the measure stations of the city of Barcelona.
    * One data set for EACH monthly measurements.
* Transport to passengers by type of boat
   * HTML tables with monthly total number of passengers.

### Data Exploration and Cleaning

The data from March 2019 is in a complete different structure than the following months.
So we start from April to October 2019 and the same months in 2020, since this is the period for high season in holiday cruises. There is an hourly daily measure in each station for each month.

I decide to group by years 2019 & 2020 respectively.

We have another dataset with the name, ID and coordinates of air mesurement stations. Simple & clean. We need the ID numbers to identify stations in the monthly reports.

The dataset with the name of pollutants are listed with their code, which is necessary to identify the codes in the monthly reports.

All the categorical data in the monthly reports is redundant and useless for our purpose (like name of province, city, and all the checkouts when a measure is collected).

All the dataset numeric records are floats, so we need to convert some columns, like station ID, pollutant ID to strings.

There is a problem with dates. These data is registrered in separate columns for Years, Months and Days. So we need to group all in one and transform to "datetime" with Pandas.

Due to the considerable amount of NaN values, the solution is to fill the next following value with the same number, since a 0 would be "no pollution" and it wouldn't be real.

After all the cleaning, the 2 csv files are ready for Tableau Visualization.

[Project Presentation Video](https://ja.cat/dataviz_project_susanna) 

[Tableau Visualization](https://public.tableau.com/views/AirQualityinTouristicHighSeason2019-2020/Story1?:language=en-US&:display_count=n&:origin=viz_share_link)
