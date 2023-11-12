# CSV files 
Here you can find all the CSV files which I have generated from the original data sets in Bigquery by specyfic SQL queries.
All the original files were imported into the Bigquery database to where data was filtered and transformed. 
* Most data did not have NA value, exception was Fat column in weight data but since only 8 users recorded their weight, further analysis of that data set would be biased and results would be insignificant.
* Duplicate values were not found.
* Daily activity records where "SedentaryActivityDistance" was not equal 0, was treated as measurment error, and thus these records were excluded from further analysis.
* Main objective of Bigquery use was to extract weekdays and hours, since POSICX function in R generate a lot of NA values. The date needed to changed from "4/12/2016 12:00:00 AM" to 24 hour format due to problems with processing AM/PM format by the R and Bigquery.

Solution to the date problem:
First I imported csv files by manualy setting schems for each column as either INT, FLOAT or STRING in case of dates. Then dates were transformed to the proper format by command:PARSE_TIMESTAMP('%m/%d/%Y %H:%M:%S %p',Time) as Time (taken from the heart rate dataset).
All SQL commands will be also added into this repository in Notepad++.
