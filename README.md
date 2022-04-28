# J296-Final-Project
Berkeley Police Stop Data 2015-2022
<br>ASC 5-year Estimates 2015-2020
* Using estimates for "Race Alone or in combination with one or more other races"
# Cleaning the data in OpenRefine
## Spreadsheet 1: Police stops from January 2015 to September 2020
* Trim white spaces from all cells, except "Createdatetime" column
* In the Race, Gender, Age, Reason, Enforcement and Car Search columns, change 359 cells with "0" to "not-listed"
* Change all "(blank)" cells to "not-listed"
* In the city column, change 2 cells with "Berkeley" to "BERKELEY"
## Spreadsheet 2: Police stops from October 2020 to April 2022
* Trim white spaces from all cells
* Under "Information Based Stop" column change "(blank)" cells to "not-listed"
* Under "If K12 School Is Stop of a student" change "(blank)" cells to "N/A"
** 8978 blank cells match the number of "false" cells under the "Is Location a K12 Public School" column
* Under "School Name" column change "(blank)" cells to "N/A"
* Under "Education Code Section" column change "(blank)" cells to "N/A"
* Under "Education Code Subdivision" column change "(blank)" cells to "N/A"
* Under "Perceived Gender", "Traffic Violation Type", "Traffic Violation Offense Codes", "Suspicion Offense Code", "Suspicion SubType", "Basis for Search", "Basis for Search Narrative", "Basis for Property Seizure", "Type of Property Seized", "Other Contraband Desc", "Warning Offense Codes", "Citation Offense Codes", "In field cite and release offense codes", "Custodial arrest Offense codes" columns change "(blank)" cells to "not-listed"
* In "Perceived Race or Ethnicity" column change 175 cells where officers noted two or more races to "Multiple-Races"
* In "Result of Stop" simplify cells into "Citation" "Warning" "Arrest" "Psychiatric hold"
** "Other" Includes non-criminal transport or caretaking transport, contacting a parent or guardian, interview card completed
** If cells include multiple results, categorize it as the most severe category listed. Arrest > Cite and Release > Citation > Warning > Psychiatric hold > Other 
# Working with the data in Google Sheets
## Spreadsheet 1:
* Divide dates and times in the "Createdatetime" column into two separate columns using "split text to columns"
* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'". Format as "plain text", then format as number "0000"
## Spreadsheet 2:
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
**Only arrests**
* Create Pivot table with Rows "year" and "enforcement", Column "Race" and Values COUNTA of "IncidentNumber". Filter "Enforcement" for only arrests
* Paste into new sheet, create new columns for percentage of total to see if there's disproportionate rates for each race
#### How do the percentages compare after the Berkeley city council ordinance passed?
#### Are there disparities in the data where officers perceived the race of the individual before the stop?
