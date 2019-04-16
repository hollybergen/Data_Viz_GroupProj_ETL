# ETL Process #

See [Jupyter Notebook file](https://github.com/hollybergen/Data_Viz_GroupProj_ETL/blob/master/Happiness_Master.ipynb)

## 1) Extract ##

### Sources of data extraction ###

* [Travel Data](https://data.worldbank.org/indicator/ST.INT.ARVL?end=2017&start=1995&year_high_desc=false)
  * International tourism rates: For 10 years from 2008 to 2018, shows number of traveler arrivals per country
  * File types: CSV
* [Country Data](https://www.kaggle.com/fernandol/countries-of-the-world)
  * Country names linked to region, population, area size, GDP, mortality and more
  * File types: CSV, JSON
* [Birth Rate](https://databank.worldbank.org/data/reports.aspx?source=gender-statistics#)
  * All countries were selected and the series called "Birth rate, crude (per 1,000 people)" was selected for the years 2016-2018. Unfortunately, only data for 2016 was available
  * File types: CSV
* [Economic Data](https://www.heritage.org/index/explore?view=by-region-country-year&u=636907699184875439)
  * Past 10 years of country wise economic index data was downloaded as a CSV file from heritage.org. Individual files were mapped with their corresponding two level and three level country codes and corresponding dialing codes using vlookups
  * File types: CSV
  
  ![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQnlnvI90j2xfHv-iNWtOBKwa_2xRDuaAQxOE9_Tk0HNGaIRSCf)
  ![](https://cdn.iconscout.com/icon/free/png-256/json-file-1-504451.png)
  
### Method ###
* Jupyter notebook/Python Pandas
   * pd.read_csv
   * pd.read_json

### Complications ###

* **Error with csv read:** ParserError: Error tokenizing data. C error: Expected 3 fields in line 5, saw 64  
  * **How error resolved:** This looked to be a parsing error. Added "error_bad_lines=False" to code to skip the offending lines
* **Error with csv read:** UnicodeDecodeError: 'utf-8' codec can't decode byte 0x92 in position 18: invalid start byte 
  * **How error resolved:** Used instead encoding = 'latin-1'

<br>
<br>
<br>

## 2) Transform ##

### Types of transformation ###
* In Python Pandas:
  * Combining multiple CSVs into single dataframe
  * Rename columns
  * Keep only columns of interest
  * Drop columns with no data

### Complications ###

* Had multiple dataframes with columns named as only the year. This could possibly cause confusion in later analysis or manipulation. **Resolution:** Rename columns to keep differentiated.
* Adding code after already run to change the name of column in DataFrame, but table using the old DataFrame had already been created. **Resolution:** Drop the old table from the db and adjust the code accordingly.

## 3) Load ##

### Final production database ### 

### Complications ###

### Final tables or collections that will be used in production database ###
