# J296-Final-Project
Berkeley Police Stop Data 2015-2022
# Cleaning the data in OpenRefine
## Spreadsheet 1: Police stops from January 2015 to September 2020
* Trim white spaces from all cells, except "Createdatetime" column
* In the Race, Gender, Age, Reason, Enforcement and Car Search columns, change 359 cells with "0" to "not-listed"
* Change all "(blank)" cells to "not-listed"
* In the city column, change 2 cells with "Berkeley" to "BERKELEY"
## Spreadsheet 2: Police stops from October 2020 to April 2022
# Working with the data in Google Sheets
## Spreadsheet 1:
* Divide dates and times in the "Createdatetime" column into two separate columns using "split text to columns"
* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'". Format as "plain text", then format as number "0000"
### Questions
#### How many police stops per each race per year
* Create a pivot table with Rows with "Year" and "Race" and Value of COUNTA of "IncidentNumber"
* Paste values only into a new sheet
++++++ INSERT SCREENSHOT 7:11PM ++++++
___***More info to come about how to compare this to city census demographics___*** <br>
#### How many arrests, warnings and citations were given out each year?
* Create pivot table with Rows with "Year" and "Enforcement" and Value of COUNTA of "IncidentNumber"
* ++++ INSERT SCREENSHOT 7:16PM ++++
#### What race/gender group was most likely to be searched? Arrested? Cited? Warned? 
* Create pivot table with Rows "Year" and "Enforcement", Column "Race" and Values COUNTA of "IncidentNumber"
* Paste into new tab, put "not listed" at the end of the row before grand total
#### How do the percentages compare after the Berkeley city council ordinance passed?
