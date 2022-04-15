# J296-Final-Project
Berkeley Police Stop Data 2015-2022
# Cleaning the data in OpenRefine
* Trim white spaces from all cells, except "Createdatetime" column
* In the Race, Gender, Age, Reason, Enforcement and Car Search columns, change 359 cells with "0" to "not-listed"
* Change all "(blank)" cells to "not-listed"
* In the city column, change 2 cells with "Berkeley" to "BERKELEY"
# Working with the data in Google Sheets
* Divide dates and times in the "Createdatetime" column into two separate columns using "split text to columns"
* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'"
