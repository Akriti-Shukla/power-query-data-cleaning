## Power Query Data Cleaning – Job Listings Dataset

This project focuses on cleaning and transforming a real-world job listings dataset using **Power Query Editor in Microsoft Excel**. The goal was to prepare the raw data for accurate analysis by organizing salary estimates, job roles, company sizes, and locations into a clean and structured format.

The uncleaned data set is downloaded from Kaggle.

---
![Role Type Vs Salary](https://github.com/user-attachments/assets/7c2f6d6f-1dad-4b9c-9917-605af76ed368)

### Objectives

- Extract meaningful salary data from messy estimates  
- Categorize diverse job titles into key role types  
- Standardize inconsistent location and state fields  
- Prepare the dataset for role-based and company size-based analysis  

---

### 🔧 Key Transformations

### Salary Segmentation

![State wise Salary Distribution](https://github.com/user-attachments/assets/5e306209-1a17-47fc-a5f9-ccfc35a4fc35)


Used **Column from Examples** in Power Query to extract:
- `Minimum Salary`
- `Maximum Salary`

```powerquery
if [Location]="California" then ", CA"
else if [Location]="New Jersey" then ", NJ"
else if [Location]="Remote" or [Location]="United States" then ", Other"
else if [Location]="Utah" then ", UT"
else [Location]
```

This helped convert inconsistent salary text into clean numeric columns ready for analysis.



![Salary by Company Size and Role Type](https://github.com/user-attachments/assets/807a9dc6-fe7f-4009-9d06-fe908703f7f1)

---

### Job Title Categorization

Created a **Custom Column** named `Role Type` to classify job titles into 5 major categories using keyword matching:

```powerquery
Role Type = 
if Text.Contains([Job Title], "Data Scientist") then "Data Scientist"
else if Text.Contains([Job Title], "Data Analyst") then "Data Analyst"
else if Text.Contains([Job Title], "Data Engineer") then "Data Engineer"
else if Text.Contains([Job Title], "Machine Learning Engineer") then "Machine Learning Engineer"
else "Other"
```

![Company Size Vs Salary](https://github.com/user-attachments/assets/4c0c2b70-c485-4b1b-9445-8dacb11e5908)



![Query Dependencies](https://github.com/user-attachments/assets/6d915e66-b070-40d9-8732-8b630c5f92ab)

### Output & Organization

- Cleaned and transformed queries were loaded into separate Excel worksheets, including:
- Salary Distribution by Company Size
- Salary Distribution by Role Type
- Combined analysis by Company Size & Role Type

### Files Included
- snapshots of the findings/insights
- Power Query - Data Cleaning - Job listing data set - excel file
- state mapping  excel file - used for merging

### Conclusion

This project highlights the importance of Power Query in preparing messy, real-world job data for accurate and insightful analysis.

