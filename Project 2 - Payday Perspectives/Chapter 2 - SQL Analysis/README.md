# [💵 Chapter 1: SQL Analysis 💵](./Spotify%20Symphony.R)

## 👋 **Welcome**  

*Welcome to Chapter 2!* This is the "SQL Analysis" section of the project!

<img src="../../Media/PP_S_SQL1.jpeg" alt="Visual of SQL" width="80%" />

## 🚀 **Foreword**

In this section we explore the Data Job Market through the use of SQL.

- What follows are 5 key SQL queries, each designed to uncover valuable insights.  

- Below, you'll find the methodology, results, and actionable insights for each query, complete with visual placeholders to enhance readability and comprehension.

Click on the respective headers to explore each SQL code further!

---

## 1️⃣ **[Query: What are the top PAYING Data Analyst jobs?](./1_top_paying_jobs.sql)**



### 📊 **Analysis:**
This query focuses on identifying the **highest-paying Data Analyst roles** across Canada and the United States, providing an overview of the top employers and job locations.

### ⚙️ **Methodology:**
- **Data Sources**: Job postings and salary data from the database.
- **Filters**: Limited to "Data Analyst" roles in Canada and the United States with verified salary information.
- **Calculations**:
  - `ROUND()` to simplify salary averages.
  - Calculated posting age in days for job relevancy.

### 📈 **Visual Insights:**

> *(Chart 1: Top 10 Paying Data Analyst Roles by Salary)*

<img src="../../Media/PP_S_Chart.png" alt="Visual of Employee Database Query" width="80%" />


### 🔑 **Key Findings:**
- Employers are primarily tech-oriented companies.
- Titles with terms like "Director" and "Senior" dominate high-paying roles.
- US highest paying jobs dominate Canadian jobs.

---

## 2️⃣ **[Query: What SKILLS are required for the top-paying Data Analyst jobs?](./2_top_paying_job_skills.sql)**

### 📊 **Analysis:**
This query identifies the most common skills **among the top 10 highest-paying** Data Analyst positions, providing insights into the technical proficiencies valued by high-paying employers.

### ⚙️ **Methodology:**
- **Data Sources**: Job postings and skills databases.
- **Joins**: Combined top-paying jobs with corresponding skill data.
- **Aggregation**: Counted occurrences of each skill in the top-paying job listings.

### 📈 **Visual Insights:**
> *Example use of CTEs within query (PostgreSQL)*
```sql
WITH top_paying_jobs AS (
    SELECT
        job_id,
        job_title,
        salary_year_avg,
        name AS company_name
    FROM
        job_postings_fact

    LEFT JOIN company_dim ON job_postings_fact.company_id = company_dim.company_id

    WHERE
        job_title_short = 'Data Analyst' AND
        job_country IN ('Canada', 'United States') AND
        salary_year_avg IS NOT NULL
    ORDER BY
        salary_year_avg DESC
    LIMIT 10
)
```

### 🔑 **Key Findings:**
1. **Top Skills by Frequency**:
   1. SQL (8 mentions)
   2.  Python (7 mentions)
   3. Tableau (6 mentions)
2. SQL and Python show the highest correlation with high salaries, emphasizing their value in this field.

---

## 3️⃣ **[Query: What are the most in-demand SKILLS for Data Analysts?](./3_top_demanded_skills.sql)**

### 📊 **Analysis:**
This query highlights the skills most frequently requested **in job postings**, offering a view of **demand trends** within the Data Analytics field.

### ⚙️ **Methodology:**
- **Data Sources**: Job postings with associated skill requirements.
- **Joins**: Linked job postings to skill data.
- **Calculations**:
  - `COUNT()` to tally occurrences of skills.
  - `GROUP BY` and `ORDER BY` to rank skills by demand.

### 📈 **Visual Insights:**
> *(Table 1: Demand of Each Skill)*

| **Skill**   | **Demand Count** |
|-------------|------------------|
| SQL         | 35,752           |
| Excel       | 28,343           |
| Tableau     | 19,942           |
| Python      | 19,172           |
| SAS         | 13,532           |

### 🔑 **Key Findings:**
- **Most Demanded Skills**:
  1. SQL
  2. Excel
  3. Tableau
- SQL and Excel lead demand by a large margin, underscoring their importance in the field.

---

## 4️⃣ **[Query: What are the top SKILLS based on salary?](./4_top_paying_skills.sql)**

### 📊 **Analysis:**
This query identifies the skills associated with the **highest average salaries**, highlighting niche competencies that could lead to higher earning potential.

### ⚙️ **Methodology:**
- **Data Sources**: Salary data and skill mentions in job postings.
- **Joins**: Connected job postings with their required skills.
- **Calculations**: Used `AVG()` to compute the average salary for each skill and sorted them to rank the highest-paying ones.

### 📈 **Visual Insights:**
> *Example use case of JOIN function within query (PostgreSQL)*
```sql
SELECT
    skills,
    ROUND(AVG(salary_year_avg), 0) AS avg_salary
FROM job_postings_fact
INNER JOIN skills_job_dim ON job_postings_fact.job_id = skills_job_dim.job_id
INNER JOIN skills_dim ON skills_job_dim.skill_id = skills_dim.skill_id
WHERE
    job_title_short = 'Data Analyst' AND
    job_country IN ('Canada', 'United States') AND
    salary_year_avg IS NOT NULL
GROUP BY
    skills
ORDER BY
    avg_salary DESC
LIMIT 25;
```


### 🔑 **Key Findings:**
- Skills linked to high salaries are often niche, suggesting potential outliers in the dataset.
- Niche technical proficiencies are often linked to specialized positions.

---

## 5️⃣ **[Query: What are the most in-demand AND highest paying SKILLS (optimal) for Data Analysts?](./5_optimal_skills.sql)**

### 📊 **Analysis:**
This query combines both **demand and salary data** to uncover the skills that offer the best combination of high pay and high demand. It serves as a roadmap for prioritizing skill development. This query is most important because it maximizes pay and demand, thereby giving me a roadmap for which skills to learn moving forward.

### ⚙️ **Methodology:**
- **Data Sources**: Skills, demand frequency, and salary data from job postings.
- **Joins**: Merged skill mentions with corresponding demand and salary data.
- **Calculations**: Used `COUNT()` for demand and `AVG()` for salary, sorted by both to identify the optimal skills.

### 📈 **Visual Insights:**
> *(Table 2: Demand and Related Salary of Each Skill)*

| Skill      | Demand Count | Average Salary |
|------------|--------------|----------------|
| SQL        | 2531         | 97,395         |
| Excel      | 1821         | 87,015         |
| Python     | 1441         | 103,284        |
| Tableau    | 1376         | 99,465         |
| R          | 894          | 100,290        |
| Power BI   | 848          | 92,976         |
| PowerPoint | 467          | 89,050         |
| Word       | 464          | 83,811         |
| SAS        | 463          | 94,193         |


### 🔑 **Key Findings:**
1. **Python** commands the highest average salary.
2. Skills like SQL and Excel remain highly in demand, offering consistent opportunities.

---

### 💻 **What I learned:**
To conclude this section, I learned that **Python** stands out as the skill commanding the highest average salary while, **SQL** and **Excel** offer the most reliable opportunities across the Data Analytics job market. This tells me that not only is database manipulation important, but also the ability to visualize the results.

**Ultimately, I learned that SQL, Excel, and Python are the most important skills for maximizing my career potential.**

---

### 🔗 **Explore the Queries**
For full SQL code, detailed comments, and execution steps, click the header links or check the respective query files in this directory!

Click [here](../) to return to the table of contents.

Yours in Solutions,  
Julian
