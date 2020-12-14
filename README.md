# BCN Neutral City

## *Pollution and cruise boats during high season (April to October) before and after Covid-19*

![Cruise Ship](http://www.barcelonaexperience.com/blog/wp-content/uploads/2015/07/carnival-cruise-terminal-barcelona-2.jpg)

### Data Sources:
[BCN Open Data](https://opendata-ajuntament.barcelona.cat/en)
[Statistics Department (Ajuntament de Barcelona] (https://www.bcn.cat/estadistica/angles/index.htm)

### Datasets

* Measured air pollutants by the air quality measurement stations of the city of Barcelona.
    * List of pollutants names with their codes.
* Air quality measure stations of the city of Barcelona.
    * Coordinates for location and names of neighbourhood.
* Air quality data from the measure stations of the city of Barcelona.
    * One data set for EACH monthly measurements.

### Data Exploration and Cleaning

The data from March 2019 is in a complete different structure than the following months.
So we start from April to October 2019 and the same months in 2020, since this is the period for high season in holiday cruises. There is an hourly daily measure in each station for each month.

I decide to group by years 2019 & 2020 respectively.

We have another dataset with the name, ID and coordinates of air mesurement stations. Simple & clean. We need the ID numbers to identify stations in the monthly reports.

The dataset with the name of pollutants are listed with their code, which is necessary to identify the codes in the monthly reports.

All the categorical data in the monthly reports is redundant and useless for our purpose (like name of province, city, and all the checkouts when a measure is collected).

All the dataset numeric records are floats, so we need to convert some columns, like station ID, pollutant ID to strings.

There is a problem with dates. These data is registrered in separate columns for Years, Months and Days. So we need to group all in one and transform to "datetime" with Pandas.


