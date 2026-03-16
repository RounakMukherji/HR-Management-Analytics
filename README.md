This project is based on an imaginary data downloaded from Kaggle, on workforce management, salary distribution and monitoring attrition rate for an MNC company since 2010 to 2025. The data contains 2M employees' data and the project has been wholly prepared in Power Bi.

# Tools & Technology Used
-	Microsoft Power Bi
-	Power Query
-	DAX Measures
-	Interactive Dashboards

# DAX I have used are
-	Total active employee = CALCULATE(COUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID]),'HR_Data_MNC_Data Science Lovers'[Status]="Active")
-	Total resigned employee = CALCULATE(COUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID]),'HR_Data_MNC_Data Science Lovers'[Status]="Resigned")
-	attrition rate = [Total resigned employee]/DISTINCTCOUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID])
-	Experience range = SWITCH(TRUE(),'HR_Data_MNC_Data Science Lovers'[Experience_Years]<1,"Freshers",'HR_Data_MNC_Data Science Lovers'[Experience_Years]<=4,"1-4 years",'HR_Data_MNC_Data Science Lovers'[Experience_Years]<=8,"5-8 years",'HR_Data_MNC_Data Science Lovers'[Experience_Years]<=12,"9-12 years","12+ years")
-	High Experience Attrition rate = DIVIDE(CALCULATE(COUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID]),'HR_Data_MNC_Data Science Lovers'[Status]="Resigned",FILTER('HR_Data_MNC_Data Science Lovers','HR_Data_MNC_Data Science Lovers'[Experience range]="9-12 years" || 'HR_Data_MNC_Data Science Lovers'[Experience range]="12+ years")),COUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID]))
-	Low Experience Attrition rate = DIVIDE(CALCULATE(COUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID]),'HR_Data_MNC_Data Science Lovers'[Status]="Resigned",FILTER('HR_Data_MNC_Data Science Lovers','HR_Data_MNC_Data Science Lovers'[Experience range]="1-4 years" || 'HR_Data_MNC_Data Science Lovers'[Experience range]="Freshers")),COUNT('HR_Data_MNC_Data Science Lovers'[Employee_ID]))
-	Running Headcount = CALCULATE([Total active employee],FILTER(ALLSELECTED('HR_Data_MNC_Data Science Lovers'[Hire_Date].[Month]),'HR_Data_MNC_Data Science Lovers'[Hire_Date].[Month]<=MAX('HR_Data_MNC_Data Science Lovers'[Hire_Date].[Month])))
-	Salary Range = SWITCH(TRUE(),'HR_Data_MNC_Data Science Lovers'[Salary_INR]<=300000,"Under 3 LPA",'HR_Data_MNC_Data Science Lovers'[Salary_INR]<=600000,"3-6 LPA",'HR_Data_MNC_Data Science Lovers'[Salary_INR]<=900000,"6-9 LPA", 'HR_Data_MNC_Data Science Lovers'[Salary_INR]<=1200000,"9-12 LPA","More than 12 LPA")

# some key Findings are
-	The Company has the highest workforce in IT department and pays maximum salary for this department.
-	Majority of employees from Finance department has experience of 1-4 years.
-	HR department has the highest number of executives who are high rated but under paid.
-	The average salary of IT Manager is the highest paid role at the company.
-	The average attrition rate since 2010 to 2025 is 19.93% that peak at 20.05% in 2018 after 2010. (The attrition rate is not perfect as the dataset doesn’t contain the existing employee number over the years)
-	Finance department has the highest attrition rate 20.13%

# Business Questions answered
-	Total active employee count 1M
-	Average salary of the company is ₹896.89
-	399k employees resigned from the company.
-	Low experience and high experience attrition rates are 9.95% and 3.60% respectively.

# Conclusion
This project demonstrates practical experience in handling real-world datasets, writing optimized DAX, and presenting insights through professional dashboards. It reflects industry-relevant analytical thinking and business understanding.

# Author
Rounak Mukherjee Business Operation Analyst | Excel | Power Bi

