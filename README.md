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
  * 8978 blank cells match the number of "false" cells under the "Is Location a K12 Public School" column
* Under "School Name" column change "(blank)" cells to "N/A"
* Under "Education Code Section" column change "(blank)" cells to "N/A"
* Under "Education Code Subdivision" column change "(blank)" cells to "N/A"
* Under "Perceived Gender", "Traffic Violation Type", "Traffic Violation Offense Codes", "Suspicion Offense Code", "Suspicion SubType", "Basis for Search", "Basis for Search Narrative", "Basis for Property Seizure", "Type of Property Seized", "Other Contraband Desc", "Warning Offense Codes", "Citation Offense Codes", "In field cite and release offense codes", "Custodial arrest Offense codes" columns change "(blank)" cells to "not-listed"
* In "Perceived Race or Ethnicity" column change 175 cells where officers noted two or more races to "Multiple-Races"
* In "Result of Stop" create a new column titled "Enforcement"
* Simplify cells into "Citation" "Warning" "Arrest" "Psychiatric hold"
   *  Officers inputed 65 different options under the result of the arrest
   *  If cells included multiple results, they were categorized as the most severe category listed. For example, five cells that noted a citation and contacting a parent or legal guardian took place, were categorized under the "Citation" category.
    *   The order of severity is 1) Arrest 2) Cite and Release 3) Citation 4) Warning 5) Psychiatric hold 6) Other
      *   Arrest category grew from 252 to 1262
      *   Cite and Release category grew from 303 to 329
      *   Citation category grew from 2126 to 2161
      *   Warning category grew from 3091 to 3154
      *   Psychiatric hold grew from 393 to 428
      *   No action occured on 1505 police stops
   * "Other" category includes officer actions like non-criminal transport or caretaking transport, contacting a parent or guardian, interview card completed.

# Working with the data in Google Sheets

## Spreadsheet 1:

* Divide dates and times in the "Createdatetime" column into two separate columns using "split text to columns"
* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'". Format as "plain text", then format as number "0000"

## Spreadsheet 2:
* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'". Format as "plain text", then format as number "0000"
### Questions
#### 1. How many traffic stops were there per year/month? How much did that change with Covid, and How much did that change with the ordinance passed in February 2021?
* In pivot table, under Rows put "Month-Year" and under values put COUNTA of "IncidentNumber"
* Copy/Paste into a new sheet
* Quick Visualization of the results
* _Three SCREENSHOTS of yearly/monthly stops_ 5:50 PM or so
#### How many arrests/warnings/citations were there per year?
