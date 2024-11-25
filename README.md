# UBC Employee Salary

## WHAT
This repo parses the .pdfs' documenting employee salaries made freely available by UBC and saves the information in a more data friendly format (.csv). </br>
The information scraped from the .pdf contains (Name, Salary, Expenses). </br>
A Python library is used to guess the gender based on the employee name. </br>
Year on year salary increases are also calculated. </br>
</br>
</br>

### Data is visualised in a Tableau dashboard. 

**https://public.tableau.com/app/profile/johann.drayne/viz/UBCEmployeeSalary/Dashboard1**

<img width="743" alt="Screenshot 2024-11-25 at 20 33 01" src="https://github.com/user-attachments/assets/3a2fb94f-94d0-458a-b011-1cf510ab060c">

---


## WHERE 
### Analysis
All analysis was done in a basic Jupyter notebook:
`src/ubc-fy/analysis.ipynb`


### RAW Data
I downloaded the datasets from UBC , but I also saved them in this repo:
`src/ubc-fy/data/financial-statements`


### OUTPUT Data
I have added 2 output .csv's:

`src/ubc-fy/data/output/salary.csv`
- name: Name of employee
- year: Year
- salary: Salary
- expense: Expense
- name_id: Unique name of employee (some employees have the same name)
- gender: Either 'male', 'female', 'unknown'

`src/ubc-fy/data/output/id-calc.csv`
- name_id: Unique name of employee (some employees have the same name)
- year_range: Year range for salary calculation, only 1 year at a time e.g. '2021-2022', '2021-2023'
- salary_amount_change: Difference in salary for the period in `year_range`
- salary_percent_change: Percentage difference in salary for the period in `year_range`
- yearly_check: True if `year_range` is a single year difference i.e. '2021-2022' -> True, '2021-2023' -> False 



---

## WHY
A fun test of data wrangling, basic feature engineering and data visualisation. </br>
This project has many potential extensions (see Disclaimer). </br>
The data in the .pdf was awfully formatted and tricky to parse. I wanted to parse the .pdf so that others could easier play with the data.  





---
---

## DISCLAIMER
I made an initial version of this projectr in 2020 when I just scraped the 2020 financial report. Recently I have been practising working with Tableau and though this would be a good project to do it. So I extended my initial code to also scrape later years. However, I found another similar project which scraped the UBC 2023 financial report. Here is a link to their repo: https://github.com/jjadeb/UBCSalary and a link to their Tableau visualisation: https://public.tableau.com/app/profile/jade.bouchard/viz/Test-UBCSalaries/Dashboard1. **NOTE:** I did not use any of their code, as I had finished parsing the .pdf's before I found their repo. However, they were also able to get information on the persons title and department which would be a great way to extend the analysis. 


---
---

### Statement of Financial Information (SOFI)
The BC Financial Information Act requires that public institutions publish certain supplementary information. This information is not audited by the external auditors. It includes payments to suppliers in excess of $25,000; employee salaries above $75,000; remuneration for our Board of Governors, and details of outstanding debt. This information is published annually, following the March 31 year end.
https://finance.ubc.ca/reporting-planning-analysis/reports-and-disclosures
 
