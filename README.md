# HR-Data

## Project Title: Incubator Hub HR Data Analysis

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

[Inferences](#inferences)


### Project Overview
---
The purpose of this data analysis project is to track the rate of attrition, that is, the figure showcasing how many employees left the incubator hub workforce over a period of time based on their departments, education fields, and gender. This analysis is carried out by the Human Resource department in order to focus on how to improve employee relationships, to boost their performances and most importantly, to improve retention rates in the organization. 

### Data Sources
---
The primary source of this HR Data is an excel document saved in CSV format which was provided by the human resource department of the Incubator Hub.

### Tools Used
---
-Power BI for:
1. Data cleaning
2. Analysis
3. Visualization

### Data Cleaning and Preparations
---
In the initial phase of data cleaning and preparation, the following tasks were completed:
1. Data loading and examination
2. Removal of Duplicate information in the data
3. Managing variables that are absent
4. Formatting and data cleaning

### Exploratory Data Analysis
---
EDA entailed examining the data to get answers to a few queries about it, such as:
- What is the total number of current employees?
- What is the total number of attrition count?
- What is the percentage of attrition rate?
- Which department has the highest rate of attrition?

### Data Analysis
---
This is where we included some basic lines of code and some of the DAX expressions used during the analysis;
```Power BI
= Table.AddColumn(#"Changed Type1", "Custom", each if [Attrition] = "Yes" then 1 else 0)

= Table.TransformColumnTypes(#"Renamed Columns",{{"Attrition Count", Int64.Type}})

= Table.AddColumn(#"Changed Type2", "Age range", each if [CF_age band] = "under 25" then 1 else if [CF_age band] = "25-34" then 2 else if [CF_age band] = "35-44" then 3 else if [CF_age band] = "45-54" then 4 else 5)

= Table.RenameColumns(#"Changed Type3",{{"Age range", "Age Sort"}})

= Table.AddColumn(#"Renamed Columns1", "Job Satisfaction Rating", each if [Job Satisfaction] = 1 then "Very dissatisfied" else if [Job Satisfaction] = 2 then "Dissatisfied" else if [Job Satisfaction] = 3 then "Satisfied" else "Very Satisfied")
```

### Data Visualization
---
![HR Data Analysis](https://github.com/user-attachments/assets/a9edf1c7-a5c2-454a-a962-42b2dc6a1cda)

### Inferences
---
1. Overall Attrition:
   - With a total of 1,470 employees and an attrition rate of 16%, approximately 237 employees (16% of 1,470) have left the organization. This suggests a significant impact on workforce stability.
2. Educational Background:
   - Employees from Life Sciences show the highest attrition, followed by those with Medical and Marketing backgrounds. This trend could suggest specific issues related to job satisfaction, industry demands, or 
     mismatches between skills and job roles for employees from these fields.
3. Departmental Trends:
   - The R&D department faces the highest attrition, followed by Sales and HR. This may indicate challenges such as high job stress, lack of career progression, or competitive offers in these departments.
4. Gender Disparity:
   - Male employees constitute the highest gender group experiencing attrition. This could reflect broader industry trends, role expectations, or specific organizational factors affecting male employees 
    disproportionately.
5. Strategic Implications:
   - Focused retention strategies should target high-risk groups, particularly employees in R&D, those with Life Sciences backgrounds, and male employees, to address the underlying causes of attrition and improve 
    retention rates.
   
