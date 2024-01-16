# PWC_Diversity_Inclusion_Dashboard
## Introduction
### Task 
Create a Power BI dashboard to represent HR data, focusing on gender-related KPIs.

### KPIs include:

- Hiring
- Promotion
- Turnover rate
- Age Group
- Performance rating
- Executive Gender Balance

## Tools
- Power BI
- DAX
## Data Preparation
The data was loaded into Power BI Desktop.

## Data Process
A new table was created for key measures.
## Data Analysis
The following measures were created using DAX:
-     % of hires were men = DIVIDE([Men], ([Men] + [Female]))
-     % of hires women = DIVIDE([Female], ([Men] + [Female]))
-     % of men promoted = DIVIDE(CALCULATE(DISTINCTCOUNT('HR_dataset'[Employee ID]), FILTER('HR_dataset', 'HR_dataset'[Gender] = "Male")), COUNT('HR_dataset'[Employee ID]))
-     % of women promoted = DIVIDE(CALCULATE(DISTINCTCOUNT('HR_dataset'[Employee ID]), FILTER('HR_dataset', 'HR_dataset'[Gender] = "female")), DISTINCTCOUNT('HR_dataset'[Employee ID]) )
-     % of employees promoted (FY21) = DIVIDE(CALCULATE(COUNT('HR_dataset'[Employee ID]), FILTER('HR_dataset', 'HR_dataset'[Promotion in FY21?] = "Yes")), CALCULATE(COUNT('HR_dataset'[Employee ID]), FILTER('HR_dataset', 'HR_dataset'[In base group for Promotion FY21] = "Yes")))  
-     % turnover = Divide(Calculate(distinctcount(HR_dataset[Employee ID]),Filter(HR_dataset,'HR_dataset'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount(HR_dataset[Employee ID]),Filter('HR_dataset','HR_dataset'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR_dataset'[Employee ID]),Filter(HR_dataset,NOT(HR_dataset[Department @01.07.2020] =BLANK()))),2))
-     average rating female = CALCULATE(AVERAGE('HR_dataset'[FY20 Performance Rating]), FILTER('HR_dataset', 'HR_dataset'[Gender] = "female"))
-     average rating men = CALCULATE(AVERAGE('HR_dataset'[FY20 Performance Rating]), FILTER('HR_dataset', 'HR_dataset'[Gender] = "Male"))
-     New hire = CALCULATE(COUNT(HR_dataset[New hire FY20?]), FILTER(HR_dataset, HR_dataset[New hire FY20?] = "Y"))
## Data Visualization
![dashboard1](https://github.com/SorathF/PWC_Diversity_Inclusion_Dashboard/blob/f29ae508d926b532f79fa0e7e00065f63e2f94e3/Dashboard%201.png)
![dashboard2](https://github.com/SorathF/PWC_Diversity_Inclusion_Dashboard/blob/f29ae508d926b532f79fa0e7e00065f63e2f94e3/Dashboard%202.png)
