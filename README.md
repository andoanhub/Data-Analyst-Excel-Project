This project use Microsoft Excel to visualizing global median salary, recruitment channels, and job type distribution for diverse IT and Data-related job titles

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

This chart provides an interactive overview of median salaries across various technical roles, countries, and job types.

**Technical Implementation:**
Uses the MEDIAN() function combined with FILTER() to perform multi-criteria analysis across the dataset. This approach allows for real-time, responsive calculations based on user-selected dimensions (Job Title, Country, and Job Type).

**Technical Implementation:** Uses the MEDIAN() function combined with FILTER() to perform multi-criteria analysis across the dataset. This approach allows for real-time, responsive calculations based on user-selected dimensions (Job Title, Country, and Job Type).

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









