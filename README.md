# J296 Final Project
The following is a data dive into traffic stops made by the Berkeley Police Department from January 2015 to March 2022. The Berkeley City Council captured national headlines last year when they approved an initiative to limit low-level traffic stops, in an effort to lessen the racial disparities in traffic stops. About 14 months after that initiative, Black and Latino drivers are still stopped, arrested and cited by police at disproportionate rates. 
<br><br>
Sources: <br> Berkeley Police Department Stop Data 1/26/2015 to 9/30/2020
<br>Berkeley Police Department Stop Data 10/1/2020 to 4/18/2022
<br>ASC 5-year Estimates 2015-2020
<br><br>
[Data Vizualization](https://infogram.com/berkeley-police-stops-1h8n6m3500kjz4x?live)<br>

# Racial Disparities Persist in Berkeley Police Traffic Stops
<br>_By Felicia Alvarez_<br>
![Berkeley Police Department](/header-image.png)<br>

Black and Latino drivers have long faced disproportionate rates of traffic stops by police in the city of Berkeley. While Berkeley leaders have made a series of efforts to reduce those disparities, racial divides remain persistent in who gets stopped, searched or arrested by Berkeley police during a traffic stop. 
<br><br>
The Berkeley City Council captured national headlines in February 2021 when they approved an initiative to limit low-level traffic stops. By directing police to only pull over drivers for the most egregious public safety risks, they hoped to lessen the racial disparities long seen in the city’s traffic stop data.
<br><br>
In the year after that initiative passed, however, Black and Latino drivers are still stopped, arrested and cited by police at disproportionate rates. 
<br><br>
Whereas Black residents only make up 10.5% of the city of Berkeley, Black drivers made up 37.3% of all police stops, according to an analysis of Berkeley police stop data. Latino drivers were also overrepresented in police stops,  making up 16.4% of stops compared to 10.9% of the city’s population, according to the U.S. Census Bureau.
<br><br>
During the same period, white and Asian drivers were underrepresented in police stop data. White drivers made up 38.8% of stops while comprising of 65.2% of the population and Asian drivers made up 7.5% of stops compared to 25.4% of the population.
<br><br>
![RaceStops](/VIZ_1.png)<br>
<br>
“There’s a disproportionality and that’s not okay,” said Berkeley Mayor Jesse Arreguín.
<br><br>
The mayor added that while the data still shows disparities, he believes the city’s recent police reforms are working and need more time.
<br><br>
“It is still early,” Arreguín said. “We are still implementing this new approach I think it’s going to be awhile before we see the outcomes in the data.”
<br><br>
Overall the disparities in who gets stopped by police have slimmed slightly. Black drivers made up 41% of all stops in February 2021 and 37% of stops in March 2022. Arrests have fluctuated over the last year, but overall Black drivers still comprise a disproportionate amount of arrests in the city compared to the city's demographics. In June 2021 and September 2021, Black drivers made up over half of the police stops that ended in an arrest. In the most recent two months -- February and March 2022 -- those percentages have dropped to below 40%.
<br><br>
The package of police reforms passed by city leaders in February 2021 was largely aimed at redirecting the “reason” for traffic stops away from “low-level” reasons such as broken tail light and more towards dangerous driving that poses a risk to public safety, according to city staff reports at the time of the vote.
<br><br>
Recent data tracking the “reason” for conducting a traffic shows fluctuations in why police pulled over a driver. From October 2021 to March 2022 the number of stops that were conducted roughly doubled to 342 stops per month. During the same period of time the number of stops conducted based on “reasonable suspicion” remained stagnant.
<br>
![ReasonStops](/VIZ_2.png)
<br><br>

Racial disparities in police stops have been well-documented in the city of Berkeley over the last decade. In 2018, the Center for Policing Equity, a non-profit research center based out of Yale University, compiled a detailed analysis of the Berkeley Police Department’s patterns in traffic stops, using data dating back to 2012.
<br><br>
At the time, the center found that Black and Latino drivers were stopped and searched at disproportionate rates compared to white and Asian drivers.
<br><br>
“The higher overall rates of stop, search, and arrest of Black and Hispanic drivers could reflect a pattern of policing discretion that is less forgiving of minor crime,” the Center for Policing Equity’s 2018 report states.
<br><br>
“Our findings are consistent with the possibility that Black and Hispanic drivers might face criminal charges in circumstances where a White driver might have received only a citation.”
<br><br>
The center also found that while police searched Black drivers at higher rates, stops with a vehicle search did not yield higher rates of arrests compared to other racial groups. The racial divide in search and arrest rates was one of several findings the center described as “opportunities for improvement.”
<br><br>
“I’m kind of frustrated, I feel like we’re making little progress,” said Councilmember Kate Harrison.
<br><br>
Harrison was part of a coalition of city leaders that led the police reform effort in 2021. While she’s still supportive of the policy, she acknowledged that it doesn’t solve the greater issue of racism among the residents making calls for service into local police.
<br><br>
“You have to deal with racism itself that comes from the public and all of us,” Harrison said. “How do you deal with that? I don’t know.”
<br><br>

Representatives from the Berkeley Police Department did not respond to requests for comment. 

# Data Diary 
## Cleaning the data in OpenRefine
### Spreadsheet 1: Police stops from January 2015 to September 2020
* Trim white spaces from all cells, except "Createdatetime" column
* In the Race, Gender, Age, Reason, Enforcement and Car Search columns, change 359 cells with "0" to "not-listed"
* Change all "(blank)" cells to "not-listed"
* In the city column, change 2 cells with "Berkeley" to "BERKELEY"
### Spreadsheet 2: Police stops from October 2020 to April 2022
* Trim white spaces from all cells
* Under "If K12 School Is Stop of a student" change "(blank)" cells to "N/A"
  * 8978 blank cells match the number of "false" cells under the "Is Location a K12 Public School" column
* Under "School Name", "Education Code Section","Education Code Subdivision"  columns change "(blank)" cells to "N/A"
* Change blank cells to "not-listed" under the following column heads: "Information Based Stop", "Perceived Gender", "Traffic Violation Type", "Traffic Violation Offense Codes", "Suspicion Offense Code", "Suspicion SubType", "Basis for Search", "Basis for Search Narrative", "Basis for Property Seizure", "Type of Property Seized", "Other Contraband Desc", "Warning Offense Codes", "Citation Offense Codes", "In field cite and release offense codes", "Custodial arrest Offense codes"
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

## Working with the data in Google Sheets

### Spreadsheet 1:

* Divide dates and times in the "Createdatetime" column into two separate columns using "split text to columns"
* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'". Format as "plain text", then format as number "0000"
* Create a new column for "Month-Year"

### Spreadsheet 2:

* Create a new column for "Year"
* Copy/Paste "Date" Column into "Year" column. Create custom time format "20'Year(30)'". Format as "plain text", then format as number "0000"
* Create a new column for "Month-Year"

# Questions
## 1) How many traffic stops were there per year/month? How much did that change with Covid, and How much did that change with the ordinance passed in February 2021?
* For Spreadsheet 1 and Spreadsheet 2, create a pivot table. Under Rows put "Month-Year" and under Values put COUNTA of "IncidentNumber"
* Copy/Paste and combine into a new spreadsheet (Spreadsheet 3)
### Annual Traffic Stops from 2015 to 2020
![AnnualStops](/QUESTION_1_A.png)
### Monthly Traffic Stops from Oct. 2020 to March 2022
![MonthlyStops](/QUESTION_1_B.png)
### Combined Monthly Traffic Stop Data 2015 - March 2022
![CombinedMonthlyStops](/QUESTION_1_D.png)<br>
**ANSWER:** On a monthly basis, Berkeley police stopped 697 to 1,206 individuals per month, from October 2019 to January 2020. After the onset of the pandemic, trafficc stops dropped as low as 64 stops in April 2020 and 36 stops in August 2020. The number of monthly stops rebounded, but is yet to pass the peaks seen in the period from 2015 to 2020. From November 2021 to March 2022, monthly traffic stops ranced from 376 to 544
## 2) How many arrests/warnings/citations were there per year (Spreadsheet 1)? Per month (Spreadsheet 2?)
The two spreadsheets were analyzed separately because enforcement data is categorized differently, and because the two spreadsheets include different ranges of time.
* Create a pivot table with Rows of "Year", Column as "Enforcement", and Values as COUNTA of "IncidentNumber"
* NOTE: Data for 2015 begins on Jan. 26, 2015. Data for 2020 ends on Sept. 30, 2020.
### Enforcement actions for each year 2015-2022
![AnnualEnforcement](/QUESTION_2_A.png)
* Create a pivot table with Rows of "Month-Year", Column as Enforcement and "Enforcement", and Values of COUNTA of "LEA Record ID"
### Enforcement actions for each month 2020-2022
![MonthlyEnforcement](/QUESTION_2_B.png)
## 3) What are the racial demographics of who gets stopped, arrested, cited, warned or other in Berkeley, and how does that compare to the city’s census demographics? 
Spreadsheet 1, by year
* Create a pivot table with Rows of "Year" and "Enforcement", Columns of "Race" and Values of COUNTA of "IncidentNumber"
* Show values as a percentage of row
* Filter out 359 cells that do not list Race and the same 359 cells that do no list what kind of enforcement occured.
### Annual Total of All Traffic Stops 2015-2020
![RacialEnforcement](/QUESTION_3_A.png)
* Copy/Paste into a new sheet. Add four new columns for census data for "Asian, Black, Hispanic and White" categories per the 5-year American Community Survey
* Insert ACS data respective to each year. Use percentages under "Race alone or in combination with one or more other races"
* There isn't a comparable category in the ACS for the "Other" category in the Berkeley police data, so don't do a comparison there
### Annual Racial Breakdown Of Enforcement Actions 2015-2022
![RacialEnforcement](/QUESTION_3_B.png)
### Monthly Racial Breakdown of Enforcement Actions 2020-2022
![RacialEnforcement](/QUESTION_3_C.png)
<br>**ANSWER:** From 2015 to 2020, Black drivers were stopped at disproportionate rates compared to other races, while Asian and White drivers were stopped less, arrested less and cited at lower rates. Hispanic drivers were pulled over at a rate roughly equal to the census demographics for the city. These disparities have continued in 2020, 2021 and 2022 so far
## 4) Are some racial demographics more likely to be searched during a police stop?
Spreadsheet 1
* Create Pivot table with Row as "Race", Columns as "Car Search" and Values as COUNTA of IncidentNumber
### Racial Demographics of Police Stops
![RacialSearch](/QUESTION_4.png)
<br>**ANSWER:** From 2015-2020, about 15% of all traffic stops resulted in police performing a car search. Black drivers were most likely to have undergo a car search, including 24.1% of all stops while Asian drivers were the least likely with 5.7% of stops resulting in a search. The rate of car searches was less than the portion of all stops most racial demographics made up (e.g. Black drivers made up 24.1% of stops but were 33.9% of all stops). The only exception was Hispanic drivers, who made up 12.9% of all traffic stops, and saw 16.3% of all car searches. 
## 5) Did the “reason” for traffic stops change after Feb. 2021?
* Create Pivot Table with Rows as Month-Year, Columns as Reason for Stop, Values and LEA Record ID
### Traffic stop "reasons" from Oct. 2020 to March 2022
![ReasonMonthly](/QUESTION_5.png)
<br>**ANSWER:** No large and immediate changes, though there may be a small dip in the number of "reasonable suspicion" stops and a small uptick in "traffic violation" stops

## 6) Did the racial demographics of who gets pulled over change after Feb. 24, 2021, when Berkeley voted to limit low-level traffic stops? Did the demographics of who gets stopped, cited or arrested change after February 24, 2021?
* Spreadsheet 2: Create a pivot table with Rows of "Month-Year" and "Enforcement", Columns of "Perceived Race" and Values of COUNTA of "LEA Record ID"
* Copy/Paste data into a spreadsheet. Sort "Month-Year" by A-Z and filter for only "Arrest"
* Filter "Month-Year" to only include March 2021-March 2022
### Monthly number of stops from March 2021 to March 2022
![RacialEnforcement](/QUESTION_7.png)
### Monthly number of arrests from March 2021 to March 2022
![RacialEnforcement](/QUESTION_8.png)
### Monthly number of citations from March 2021 to March 2022
![RacialEnforcement](/QUESTION_8.png)
<br>**ANSWER:** Overall the disparities in who gets stopped by police have slimmed slightly. Black drivers made up 41% of all stops in February 2021 and 37% of stops in March 2022. Arrests have fluctuated over the last year, but overall Black drivers still comprise a disproportionate amount of arrests in the city compared to the city's demographics. In June 2021 and September 2021, Black drivers made up over half of the police stops that ended in an arrest. In the most recent two months -- February and March 2022 -- those percentages have dropped to below 40%. 
