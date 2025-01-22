# Excel Job Salary Analysis
 Analysis on job salary data using advanced Excel functions such as Power Query, DAX, and Power Pivot

## Introduction
💡 This data science jobs salary analysis was created to help potential job seekers (including myself) to investigate what skills employers request and how they could land more pay.

## Data
Data from: https://www.lukebarousse.com/excel

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via the link above. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Questions to Analyze

To understand the data science job market, I wanted to investigate for the the following:

1. **Do more skills result in better pay?**
2. **What are the salaries for data jobs in different countries?**
3. **What are the top data science skills requested by employers?**
4. **What are the associated salaries with these highly requsted skills?**

## 1️⃣ Do more skills result in better pay?

### 🔍 Skill: Power Query (ETL)

#### 💻 **Extract**

- Power Query was used to extract the original data which can be found here [data_jobs_salary_all.xlsx](https://github.com/user-attachments/files/18500124/data_jobs_salary_all.xlsx)
  and the following two queries were created:
    - 👨‍💼 Query with all of the data science jobs information.
    - 🛠️ The second query listing the required skills for each job ID.
 
#### 🔄 **Transform**

- Each query was then transformed by removing unnecessary columns, changing column types, cleaning text to eliminate specific words, and trimming excess whitespace.
  
- 📊 data_jobs_all

![data_jobs_all_query](https://github.com/user-attachments/assets/616078f5-8f8d-4215-8a98-c95f70c21377)

 - 🛠️ data_job_skills

![data_jobs_skills_query](https://github.com/user-attachments/assets/cb779efb-ff96-4cf5-9fbc-e7f3861a5816)

#### ⌛ **Load**

- Both transformed queries were loaded into the workbook, allowing for subsequent analysis.
  
- 📊 data_jobs_all

![data_jobs_all_load](https://github.com/user-attachments/assets/62d68097-2d56-4b43-8be6-1a3d4840e4bd)

- 🛠️ data_job_skills

![data_jobs_skills_load](https://github.com/user-attachments/assets/47eea201-4f0f-4620-ab9f-2673506ab270)


### 💡Analysis & Insights

- 📈 Overall, yhere is a positive correlation between the number of skills requested in job postings and the median salary. This is as you would expect especially in the data science job market where more complex and techical roles such as Senior Data Scientists would require a lot of skills, and hence attract greater salaries.
- However, when you compare Senior Data Engineer and Senior Data Scientist, it can be seen that the Senior Data Scientist pays on average higher than Senior Data Engineer despite the job requiring less skills (5.3 v 8.1).
- For someone choosing between these roles, the Senior Data Scientist role would be a logical choice (assuming they were deciding which skills to learn).
- 💼 Roles that require fewer skills such as Business Analyst for example, tend to offer lower salaries. At around 3 skills required, this suggests that less specialized skill do not command the higher salaries.
- The exact skills required for each role will be analyzed later, which will provide even greater context to this analysis.
  
![Do more skills result in better pay](https://github.com/user-attachments/assets/fe7598ed-e2fe-4ee8-b893-8723541f4fec)

#### **🤔 Key takeaway**
- The visualization above emphasizes the value of acquiring multiple relevant skills, particularly for those aiming for higher-paying roles.

## 2️⃣ What are the salaries for data science jobs in different countries?





















## Conclusion

## ✅ What I learned from this project 

During this project, I gained practical experience in advanced Excel tools such as Power Query, DAX, and Power Pivot which enhanced my ability to analyze complex datasets, and derive meaningful insights for the intended audience of a job seeker. 

This project has re-iterated the importance and value of data visualization for various stakeholders.

