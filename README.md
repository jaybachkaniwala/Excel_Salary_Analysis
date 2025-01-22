# Excel Job Salary Analysis
 Analysis on job salary data using advanced Excel functions such as Power Query, DAX, PowerPivot and PivotChart.

## Introduction
💡 This data science jobs salary analysis was created to help potential job seekers (including myself) to investigate what skills employers request and how they could land more pay.

## Skills/Tools Used
- **Power Query**
- **Data Analysis Expressions (DAX)**
- **PowerPivot**
- **PivotChart**
  
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
The following two queries were created:
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

### 🧮 Skills: PivotTables & DAX

#### 🔲PivotTable

- 🔢 A PivotTable was created using the Data Model created with Power Pivot.
- 📊 The `job_title_short` was moved to the rows area and `salary_year_avg` into the values area.
- 🧮 I then added a new measure to calculate the median salary for United States jobs, as I wanted Median values rather than Average.

 ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
 ```

#### 🧮 DAX

- To calculate the median yearly salary I used Data Analysis Expressions (DAX).

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```
    
### 💡Analysis & Insights

- 💼 Job roles such as Senior Data Scientist and Senior Data Engineer command higher median salaries both in the US and internationally, indicating the world-wide demand for high-level technical data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the U.S.
- There could also be more unmatched demand in the U.S, althought more data would be required to explore this in detail.
  
![US v Non-US Median Salaries](https://github.com/user-attachments/assets/74640046-5364-4605-9086-6c172ccf9eda)

#### **🤔 Key takeaway**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top data science skills requested by employers?

### 🔧 Skill: PowerPivot

#### 💪 PowerPivot

- 📔 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between the two tables using the `job_id` column to match on.

![Relationship Diagram](https://github.com/user-attachments/assets/9f45886c-8e84-463c-91d1-4e6a604b827a)

#### 📃 PowerPivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create new measures
  
![Power Pivot](https://github.com/user-attachments/assets/1396b8ec-e919-493f-b563-cd0bbdba8141)

### 💡Analysis & Insights

- 💻 SQL and Python dominate as the top skills likely to be requsted by employers in data-related jobs, reflecting their foundational role in data processing and analysis.
- 📊 Visualization tools such as Tableau are 3rd on the list highlighting the importance of communicating insights to stakeholders in a clear and concise manner.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

![What are the top skills to learn](https://github.com/user-attachments/assets/ff475e02-6846-4f00-8b41-1895bc0cecdb)

#### **🤔 Key takeaway**

- This serves as a guide to the prevalent skills in the industry, and to indicate the training they should undertake so they can focus on the most impactful technologies that employers value, which will allow candidates to remain competitive and in-demand.
- SQL and Python are both seen in over 50% of job postings and hence should serve as a foundational layer upon which to build and specialize.

## 4️⃣ What are the associated salaries with these highly requested skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
  
### 💡Analysis & Insights

- 💰 Higher median salaries are associated with skills like Spark, AWS, Java, suggesting that specialized cloud computing and big data skills are highly rewarded. This is in line with out previous analysis.
- However, they tend to seen less in data science job postings with a higher 'skill likelihood', which makes sense due their specialized nature.
- 📉 The opposite is generally true for more generic tools such as Excel, and SQL.

![What is the pay for the top 10 skills](https://github.com/user-attachments/assets/9c4baafc-111d-476b-81a8-214b561efb91)

## Conclusion

- 🔍 Regarding skills to learn, an effective strategy for job seekers would be to learn the more commonly requested skills such as SQL, Excel and Python especially for those that are new to the job market with limited experience.
- 🔥 They could then look to develop more specialized skills in Big Data and Cloud technologies as they look to progress their careers and increase their earning potential.

## ✅ What I learned from this project 

During this project, I gained practical experience in advanced Excel tools such as Power Query, DAX, PowerPivot and PivotChart which enhanced my ability to analyze complex datasets, and derive meaningful insights for the intended audience of a job seeker. 


