# ETL Process #

## 1) Extract ##

### Sources of data extraction ###

* [Travel Data](https://data.worldbank.org/indicator/ST.INT.ARVL?end=2017&start=1995&year_high_desc=false)
  * For 10 years from 2008 to 2018, shows number of traveler arrivals per country
  * File types: CSV
* [Country Data](https://www.kaggle.com/fernandol/countries-of-the-world)
  * Country names linked to region, population, area size, GDP, mortality and more
  * File types: CSV, JSON
* [Birth Rate](https://databank.worldbank.org/data/reports.aspx?source=gender-statistics#)
  * All countries were selected and the series called "Birth rate, crude (per 1,000 people)" was selected for the years 2016-2018. Unfortunately, only data for 2016 was available
  * File type: CSV
  
  ![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQnlnvI90j2xfHv-iNWtOBKwa_2xRDuaAQxOE9_Tk0HNGaIRSCf)
  ![](https://cdn.iconscout.com/icon/free/png-256/json-file-1-504451.png)
  
### Method ###
* Jupyter notebook/Python
  * Pandas
   * pd.read_csv
   * pd.read_json

### Complications ###

* **Error with csv read:** ParserError: Error tokenizing data. C error: Expected 3 fields in line 5, saw 64  <br>
  * **How error resolved:** This looked to be a parsing error. Added "error_bad_lines=False" to code to skip the offending lines. <br>

* **Error with csv read:** UnicodeDecodeError: 'utf-8' codec can't decode byte 0x92 in position 18: invalid start byte <br>
  * **How error resolved:** Used instead encoding = 'latin-1'<br>

<br>
<br>
<br>

## The type of transformation needed for this data (cleaning, joining, filtering, aggregating, etc) ##

## The type of final production database to load the data into (relational or non-relational). ## 

## The final tables or collections that will be used in the production database. ## 
