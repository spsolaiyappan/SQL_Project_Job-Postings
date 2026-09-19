# Data Jobs Analysis

## Introduction
- What skills are companies actually looking for?
- Which data roles are in demand?
- Does working remotely mean higher pay?
- And most importantly — what skills are worth learning? 🎯

This project uses PostgreSQL + SQL to explore a job postings dataset and answer the below mentioned questions through data-driven analysis 🚀

### 💡 Questions I wanted to answer

    🏆 What are the top data job roles?

    💰 What skills are associated with the top-paying data jobs?

    🔥 Which skills are most in demand, and what are their minimum and maximum salaries?

    🏠 Which skills are associated with higher average salaries for work-from-home roles compared with overall average salaries?

    🎯 What skills offer a strong combination of job demand and salary potential?


🔍 SQL Queries? Check them out here [SQL_Queries_Folder](/SQL_Code_Files/)

 ## Database Structure
The project uses four relational tables:

| Table | Purpose |
| ----- | ------- |
|💼job_postings_fact |	Job titles, salaries, locations, WFH status, and other job information|
|🏢 company_dim|	Company information|
|🛠️ skills_dim|	Individual skills and skill types|
|🔗 skills_job_dim|	Connects jobs with their required skills|

### Database relationship
                 company_dim
                     │
                     │ company_id
                     ▼
              job_postings_fact
                     │
                     │ job_id
                     ▼
              skills_job_dim
                     │
                     │ skill_id
                     ▼
                 skills_dim


The database uses primary keys, foreign keys, and indexes to maintain data integrity and improve query performance.

## 🛠️ Tools I Used

🐘 PostgreSQL — Database creation & analysis

🔗 GitHub — Project documentation & version control

📝 VS Code — Query development

📊 Power BI — Used to visualize SQL query results and present key findings

### SQL concepts used

``` JOIN ```
 ``` GROUP BY ``` 
``` ORDER BY ```
``` COUNT() ```
``` AVG() ```
``` MIN() ```
``` MAX() ```
``` CTE ```
``` ROW NUMBER ```
``` HAVING ```
``` PARTITION BY ```
``` Filtering ```
``` Ranking ```

## 📈 Analysis
### 🏆 1. What Are the Top Paying Data Jobs?


The first analysis focuses on identifying high-paying data roles from the job postings dataset.

The goal was to explore which data job titles have the highest salary levels and understand how compensation differs across roles.

***Key SQL concepts:***  
- ```Row Number()``` 
- ``` GROUP BY``` 
- ``` ORDER BY```

***Visualization for the queried results***

  ![alt text](image.png)

---
                                                                        
### 🛠️ 2. What Skills Are Associated With High-Paying Data Jobs?

After identifying high-paying data roles, I looked at the skills associated with those positions.

This analysis connects the job postings table with the skills tables to explore which technical skills appear in high-paying positions.

This required working across multiple related tables and reinforced my understanding of JOINs and many-to-many relationships.

***SQL concepts practiced***

- ```JOIN```
- ```CTE```
- ```ORDER BY```  


---
### 🔥 3. What Skills Are in Demand?

The third analysis looks at the number of job postings associated with individual skills and calculates the minimum and maximum salary associated with those skills.

The results highlight some clear patterns:

🐍 **Python** dominates for Data Science roles

Python appeared in 3,689 Data Scientist job postings, making it the most frequently requested skill in the Data Scientist results.

🗄️ **SQL** is everywhere

SQL showed strong demand across multiple roles:

Role |	SQL Job Count |
---- | ---------------|
🧠 Data Scientist |	2,770 |
📊 Data Analyst |	2,574 |
⚙️ Data Engineer |	2,554 |

This makes SQL one of the most consistently requested skills across the data job market.

**📊 Analyst-focused skills**

For Data Analysts:

* Excel — 2,903 postings
* SQL — 2,574 postings
* Python — 1,954 postings
* Tableau — 1,478 postings
* R — 1,173 postings
* Power BI — 1,017 postings

**⚙️ Engineering-focused skills**

For Data Engineers:

- SQL — 2,554 postings
- Python — 2,278 postings
- AWS — 1,663 postings
- Azure — 1,205 postings
- Spark — 1,070 postings

***💡 Takeaway***

The analysis suggests that SQL and Python have broad demand across multiple data career paths, while other technologies become more specialized depending on the role.

***Visualization for the queried results***

![alt text](image-1.png)

---

### 🏠 4. Skills & Work-From-Home Salaries


I compared overall average salaries with average salaries for work-from-home positions associated with individual skills.

Some interesting examples:

|Role |Skill | Overall Avg. | WFH Avg.|
|-----|------|-------------|--------|
|⚙️ Data Engineer|	GDPR|	$180,792|	$199,359|
|⚙️ Data Engineer|	Rust|	$182,635|	$199,136|
|🧠 Data Scientist|	Watson|	$159,758|	$215,000|
|🧠 Data Scientist|	Atlassian|	$161,327|	$191,438|
|⚙️Data Engineer| php | 152043 | 105000 |

***Key Findings***

Some skills show higher average salaries in work-from-home positions than their overall averages.

However, not every skill followed the same pattern.

For example, Dplyr showed an overall average salary of $160,645, compared with $135,000 for work-from-home positions.

***🎯 Takeaway***

The relationship between skill + role + remote work + salary isn't straightforward.

This suggests that remote work does not automatically result in higher compensation for every skill, and salary can vary depending on the role, skill, and other job characteristics.

***Visualization for the queried results***

 ![alt text](image-2.png)
 
---
### 🎯 5. What Skills Should You Learn?

This was the question I found most interesting.

Instead of looking only at salary, I looked at job demand + salary potential to identify skills that could provide a strong combination of opportunity and compensation.

#### **📊 Data Analyst**

|🏅|	Skill	|Job Count|	Max Salary|
|---|---------|----------|-------------|
|1|	Excel|	2,903|	$385K|
|2|	SQL|	2,574|	$445K|
|3|	Python|	1,954|	$445K|
|4|	Tableau|	1,478|	$275K|
|5|	R|	1,173|	$240.5K|
|6|	Power BI|	1,017|	$232.2K|
|7|	SAS|	864|	$216.8K|

 ***💡 Analyst takeaway***

Excel, SQL, Python, and Tableau stand out because they combine strong job demand with substantial salary potential.

#### **⚙️ Data Engineer**
|🏅|	Skill|	Job Count|	Max Salary|
|----|--------|----------|--------------|
|1|	SQL|	2,554|	$445K|
|2|	Python|	2,278|	$410K|
|3|	AWS|	1,663|	$400K|
|4|	Azure|	1,205|	$400K|
|5|	Spark|	1,070|	$445K|
|6|	Java|	914|	$445K|
|7|	Snowflake|	815|	$301.3K|

***💡 Engineering takeaway***

For Data Engineering, SQL + Python + cloud technologies form a particularly strong combination, with AWS and Azure showing significant demand.

#### **🧠 Data Scientist**
|🏅	|Skill|	Job Count	|Max Salary|
|-------|-----|--------------------|-----------|
|1	|Python	|3,689	|$870K|
|2	|SQL	|2,770	|$850K|
|3	|R	|2,041	|$361K|
|4	|AWS	|883	|$320K|
|5	|Spark	|902	|$315.8K|
|6	|Tableau	|948	|$311.8K|
|7	|SAS	|812	|$266.4K|

***💡 Data Science takeaway***

Python and SQL clearly stand out in terms of job count and salary potential, followed by R, Spark, AWS, and Tableau.

***Visualization for the queried results***

![alt text](image-3.png)

**Note:** *The salary figures represent the minimum and maximum values present in the dataset. Some maximum values are unusually high, so they should not be interpreted as typical salaries for these roles.*

## 🧠 What I Learned?

This project wasn't just about writing SQL queries — it was about learning how to ask better questions of data.

* 🔑 Technical takeaways

* 🗄️ Designed a relational database using fact and dimension tables
* 🔗 Worked with primary keys and foreign keys
* 🔄 Analyzed many-to-many relationships between jobs and skills
* 🔍 Joined multiple tables to combine information
* 📊 Used aggregation functions such as COUNT(), AVG(), MIN(), and MAX()
* 🧩 Used CTEs to structure complex analysis
* 📈 Compared salary and job-demand metrics
* 🎯 Turned raw job-posting data into practical insights
* 🔍 Used Power BI to transform query results into visual insights

***💭 Analytical takeaway***

One of the biggest lessons was that the highest salary doesn't necessarily mean the best skill to learn.

A skill with a slightly lower salary but thousands of job opportunities may provide more potential career opportunities than a skill associated with a very high salary but only a handful of postings.

That's why I considered both demand and salary when evaluating skills.

## 🚀 Conclusion

**This project started with a simple question:**
 *"What does the data job market actually look like?"*

Using **SQL**, I explored the relationship between roles, skills, salaries, and remote work.

**A few key insights stood out:**

* 🐍 Python is highly demanded for Data Science.

* 🗄️ SQL consistently appears across Data Analyst, Data Engineer, and Data Scientist roles.
* 📊 Excel remains highly relevant for Data Analysts.
* ☁️ AWS & Azure are important skills for Data Engineering.
* 🏠 Remote salary outcomes vary significantly by skill and role.
* 🎯 Demand + salary together provide a better perspective than either metric alone.


Overall, this project gave me hands-on experience using SQL to move from raw data → analysis → insights → practical conclusions.