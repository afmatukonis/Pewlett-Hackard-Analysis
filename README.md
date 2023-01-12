# Pewlett-Hackard-Analysis

**Overview**

This assignment was to help Bobby at Pewlett Hackard with figuring out the number of employees that are retiring and what can be done to help mitigate that mass turnover. One solution was to offer a mentor-mentee program for those about to enter retirement, who can step into a part-time role instead of retiring completely and mentor new hires. Using QuickDBD.com, pgAdmin 4, and postgres(SQL) I was able to take six different tables and combine them into new tables that provided information on who would be eligible for the new mentorship program. 

**Results**

The six initial csv files included the following informaion; employee ID number, deptartment number and department names, manager employee numbers, employee salaries, employee titles, employee start dates and end dates, birthdates, and hire dates. Using the aformentioned tools we created a diagram to show the relationships between each of the csv files and then constructred primary and foreign keys that allowed us to create new tables in SQL. 

![ERD](https://user-images.githubusercontent.com/118235205/212041565-fef4f6ee-c84d-4b4c-8378-146567603122.png)

To first determine how many employees were nearing retirement we selected all the employees born between 1952 and 1955 as well as their titles. We created a new table to view this information called retirement_titles, but there were many duplicates due to title changes. To combat this we performed another SQL query that only viewed the most recent title and created a table called unique_titles. This showed that over 70,000 employees were going to be nearing retirement. 

--Deliverables--

Deliverable 1 asked us to figure out the total number of employees nearing retirement and if certain titles were going to be affected more than others. 

![Screen Shot 2023-01-12 at 2 28 38 AM](https://user-images.githubusercontent.com/118235205/212042958-e7828da8-b20d-4a62-90f7-413799a73884.png)

Based on this data we can see that senior engineer and senior staff will be the most affected during this retirment move.

Deliverable 2 allowed us to determine how many of the people retiring would be eligible for the mentorship program. To do this we created a new table called mentopship_eligibility that joined dept_emp table and employees and kept, emp_no, first_name, last_name, birth_date, dept_emp from_date, to_date, and titles, and then ordered by their emp_no. This showed us just who exaclty was elibible. 

![Screen Shot 2023-01-12 at 2 34 35 AM](https://user-images.githubusercontent.com/118235205/212044277-ee033e11-2361-4eff-8833-c4c43ec324ed.png)

+ 72,458 total employees are nearing retirement
+ 1,549 employees are eligible for the mentorship program. 
+ 25,916 Senior Engineer and 24,926 Senior Staff compose 50,842 or 70.16% of the retiring workforce is senior staff. 
+ Only allowing mentors from the year 1965 greatly limits the eligible results. 

**Summary**

To address the mass exodus of 72,458 employees, over 70,000+ new employees will need to be hired, with the bulk replacing senior staffing positions. This is not reasonable as new hires will lack the experience needed for senior positions. A solution is to have the senior staff and engineers take on the mentor role and slowly bring up regular engineers and staff to a senior level while having new hires replace those brought up. By allowing more mentors from more years, not only 1965, the mentor pool will grow. A query would be to modify the mentorship one and include more years than 1965.

![change_mentor_query](https://user-images.githubusercontent.com/118235205/212046899-4ff2f2cc-ee1d-49d6-8d50-4fd060cbe7b2.png)

