# PWC-Task-3-Inclusion-and-Diversity-Dashboard
## Problem Statement:
Visualizing and defining KPIs in hiring, promotion, performance and ratings, turnover , executive gender balance , age groups.
Generating a visualisation for the HR manager that reflect all required KPI's in a dashboard.
Calculating Following measures for defining required KPIs:
- No of of men
- No of women
- No of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % of hires women
- turnover 
- Average performance rating: men
- Average Performance rating: women
- Possible Root cause analysis
## Datasource and Preparation
Data set for this task was provided by PWC Diversity and Incluion dataset. [03 Diversity-Inclusion-Dataset.xlsx](https://github.com/AnjaliM-9/PWC-Task-3-Inclusion-and-Diversity-Dashboard/files/14671951/03.Diversity-Inclusion-Dataset.xlsx)
The dataset contained 501 rows and 31 columns.
Steps performed for Data transformation in Power Query after the dataset loaded into Microsoft Power BI Desktop for modeling:
- Removed Unnecessary columns
- Removed Unnecessary rows
- Filtered out missing values rows from data set
Each of the columns in the table were validated to have the correct data type
## Data Modeling
Diversity and Inclusion data set has 4 tables Pharma AG Group, Backing 1 , Backing 2 , Backing 3 , Backing 4 .
![Picture1](https://github.com/AnjaliM-9/PWC-Task-3-Inclusion-and-Diversity-Dashboard/assets/155083462/1de3c104-6336-417b-b748-52edbbaac09c)
## Data Analysis (DAX)
Following are the measures created:-
- No of of men = ``` CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male")) ```
- No of women = ```  CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female")) ```
- No of leavers = ``` CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]),FILTER('Pharma Group AG','Pharma Group AG'[FY20 leaver?]="Yes"))```
- % employees promoted (FY21) = ``` CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Promotion in FY20?]="Y")+CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Promotion in FY21?]="Yes")```
- % of hires men =```DIVIDE('Pharma Group AG'[# of men],'Pharma Group AG'[# of men]+'Pharma Group AG'[# of women])*100```
- % of hires women = ```DIVIDE('Pharma Group AG'[# of women],'Pharma Group AG'[# of women]+'Pharma Group AG'[# of men])*100```
- turnover = ``` employee turnover =```DIVIDE('Pharma Group AG'[# of leavers],COUNT('Pharma Group AG'[Employee ID]),0)*100 ```
- Average performance rating: men =``` CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"))```
- Average Performance rating: women =```CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"))```
Calculated Column:
```YEAR = YEAR('Pharma Group AG'[Last hire date])```
## Dashboard (Data Visualization)
### Welcome page
![0001](https://github.com/AnjaliM-9/PWC-Task-3-Inclusion-and-Diversity-Dashboard/assets/155083462/461efe64-48df-4ad1-b6bf-419e72527708)
### Dashboard 1
![0002](https://github.com/AnjaliM-9/PWC-Task-3-Inclusion-and-Diversity-Dashboard/assets/155083462/a0af9153-1239-4c90-96f9-932ff18da84a)
### Dashboard 2
![0003](https://github.com/AnjaliM-9/PWC-Task-3-Inclusion-and-Diversity-Dashboard/assets/155083462/9287b1c5-930b-4555-8c8d-3022de975704)
### Possible Root cause Analysis
![0004](https://github.com/AnjaliM-9/PWC-Task-3-Inclusion-and-Diversity-Dashboard/assets/155083462/716c51b5-d190-4eb9-b2e3-00bc66a5479e)
## Insights!
Following conclusions could be drawn:
- 41 % Female hires of the year and 59 % Male hires of the years.
- Average Rating Female 2.42%
- Average Rating Male 2.41%
- Companies being benefited by diversity and inclusion are: Germany, France, Italy, Switzerland.
- More women are hired at junior, senior officer and manager level.
- Promotion of women workforce is decreased at higher levels.
- On the other hand females has slightly higher performance rating specially at senior manager level.
- Year 2017 has a peak in hiring trend.
- Almost no increase of women ratio at executives level


