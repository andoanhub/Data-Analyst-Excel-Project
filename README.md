## This project use Microsoft Excel to visualizing global median salary, recruitment channels, and job type distribution for diverse IT and Data-related job titles

# 📊 Dashboard Preview

https://github.com/user-attachments/assets/47fedf3f-aa45-47dd-a750-8007f7cc1f8f


# 🎯 Project Objectives
- Median Salary: Calculate the median salary by job title and region.
- Platform Efficiency: Identify which platforms have the most job postings per country.
- Job Type Analysis: Analyze median salary and total job volume for different employment types (Full-time, Part-time, Contract, etc.).
  

# 🛠 Excel Skills Used
- Charts
- Formulas and Functions
- Data Validation
  

# Dashboard Build
## 📊 Median salary for each job - Bar Chart

https://github.com/user-attachments/assets/b7935cd0-5a96-4857-b132-98b84239a558

This chart provides an overview of median salaries across various technical roles.
**Median Salary** feature allows users to analyze median salary trends based on job titles, countries and job type.

**Technical Implementation:**
Uses the MEDIAN() function combined with FILTER() to perform multi-criteria analysis across the dataset. This approach allows for real-time, responsive calculations based on user-selected dimensions (Job Title, Country, and Job Type).


```excel
=MEDIAN(
    FILTER(
        jobs[salary_year_avg], 
        (jobs[job_title_short] = title) * 
        (jobs[job_country] = country) * 
        (jobs[job_schedule_type] = type)
    )
)
```

**Visual Highlighting Technique:**
To enhance user experience, I implemented a dynamic highlighting feature for the bar chart.
**Logic:** I created a helper column using an "IF" statement to isolate the selected job title's salary data.

## 🌍 Country median salary and top job platform - Map Chart



https://github.com/user-attachments/assets/98080981-64cc-424d-ae7d-419fe832d147



This interactive map provides a geographical overview of salary.
**Top Platform** feature that specific roles are most frequently listed. It allows users to quickly identify the most effective platforms for their target job title within any selected country.
**Technical Implementation:**
To dynamically retrieve the top-performing job platform, I implemented an array-based search formula. This logic filters listing volume by country and title, identifies the platform with the highest frequency, and returns its name.


```excel
=INDEX(
    UNIQUE(Data!D2:D32673), 
    MATCH(
        MAX(COUNTIFS(Data!D2:D32673, UNIQUE(Data!D2:D32673), Data!K2:K32673, country, Data!A2:A32673, "*" & title & "*")), 
        COUNTIFS(Data!D2:D32673, UNIQUE(Data!D2:D32673), Data!K2:K32673, country, Data!A2:A32673, "*" & title & "*"), 
        0
    )
)
```
How it works:
- Frequency Analysis: Uses COUNTIFS with wildcards (*) to perform a partial match on job titles, ensuring accurate counts across all platforms.
- Peak Identification: The MAX function evaluates the posting distribution, while MATCH locates the specific platform with the highest volume.
- Dynamic Retrieval: INDEX combined with UNIQUE ensures the map updates automatically based on the user's specific filter criteria (Country & Job Title).


## 📊 Job Type and Count - Bar Chart
<img width="528" height="496" alt="Job_Type" src="https://github.com/user-attachments/assets/daadc4b3-de81-40db-a262-8dfb54b7624f" />
This bar chart compares median salaries across different employment types (e.g., Full-time, Part-time, Contractor)
**Job Count** feature that calculates the total number of job postings for your selected Job Title, Country, and Job Type, allowing you to quickly gauge market demand and competition.


# Summary
This interactive dashboard is a personal project based on an online course, designed to provide a clear overview of the IT job market by:
- Benchmarking Salaries: Providing median salary insights by role, region, and job type.
- Optimizing Search: Identifying the most relevant job platforms for specific needs.
- Measuring Opportunity: Tracking job counts to gauge real-world demand.
This project showcases how Excel can be leveraged as a powerful, professional tool for data-driven decision-making.

