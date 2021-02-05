# Pewlett_Hackard_Analysis
## Overview

In this analysis, we used SQL queries through Postgres in pgAdmin to create tables using information contained in our six existing databases. Specifically, we were tasked with creating tables that contained the number of retiring employees by title and the current employees eligible for the mentorship program. In order to make these new tables, we merged and filtered the information that we had on our existing databases. 

## Analysis

An overview of the process and results of our data analysis is outlined below:

### Retiring Employees by Title
- In our first deliverable, we started by querying data from the existing 'employees' and 'titles' datasets. We then filtered the table to show only employees born between 1952 and 1955. We used the query below to obtain the 'retirement_titles' table. 

![Code for retirement_titles](/Screenshots/D1.1_query.png)

A sample from the retirement_titles table is shown below: 

![Table for retirement_titles](/Screenshots/D1.1_table.png)


Although this dataset succeeds in containing all employees born between 1952 and 1955, it should be noted that there are employees listed in this table that no longer work for the company. 

- Next, we used the 'DISTINCT' statement to remove the rows that listed the same employees more than once. We used the 'ORDER BY' statement to show only each employees most recent position. The query and a sample from the resulting 'unique_titles' table is shown below: 

![Code for unique_titles](/Screenshots/D1.2_query.png)

![Table for unique_titles](/Screenshots/D1.2_table.png)

- Next, we queried the count of retiring titles in each department, and listed the departments in descending order by count of retirees. The query and the resulting 'retiring_titles' table are shown below. 

![Code for retiring_titles](/Screenshots/D1.3_query.png)

![Table for retiring_titles](/Screenshots/D1.3_table.png)

### Current Employees Eligible for Mentorship Program
- For our final deliverable, we created a table that showed employees that were eligible to participate in a company sponsored mentorship program. In order to generate this table of employees, we filtered for all employees born in 1965. We used the 'DISTINCT' statement once again so that employees who have held multiple positions at the company (and are therefore listed multiple times in the datebase) would only show up once in the list. In addition to filtering by 'birth_date', we also filtered by 'to_date' so that only the current employees in their most recent positions would be shown in the table. The query and a sample from the resulting 'mentorship_eligibility' table are shown below: 

![Code for mentorship_eligibility](/Screenshots/D2_query.png)

![Table for mentorship_eligibility](/Screenshots/D2_table.png)

## Summary
Question: How many roles will need to be filled as the "silver tsunami" begins to make an impact?

Answer: As mentioned above, the number of retirement-aged employees currently working at the company is actually less than the amount of retirement aged employees listed in 'retiring_titles' table listed above. The 'retiring_titles' table lists the number of retirement aged people who have ever worked for the company, not just the current employees. The table below shows the number of retirement age workers who are current employees of the company: 

![Table for current_retirees](/Screenshots/S1_table.png)

This above table shows the amount of people who will soon be retiring in each department. If all of these job roles are still necessary, the company will need to fill all these jobs. 

Question: Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

Answer: The following table shows the number of mentor-elligible employees born in 1965 per department:

![Table for 1965_mentors](/Screenshots/S2_table.png)

In order for there to be enough mentors to cover the amount of new positions, management should widen their age range of possible mentors. See below for further thoughts on this process. 


Here are some additional considerations for company leaders: 
1. Which of the jobs left vacant by retiring employees can be filled by existing employees, and which of these positions will require hiring new employees? 

2. For the project, we were asked to show the amount of available mentors born in 1965. In order to properly mentor all new employees, it will be necessary to expand to other ages of current employees when designating mentors. Management should consider which age range it wants to use for mentors, and a new database query should be run with an expanded 'birth_date' range. 




