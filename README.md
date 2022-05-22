## **<h1 align="justify"> surfs_up**
Advance Data Storage and Retrieval with Jupyter Notebook, SQLite and SQLAlchemy.
	
---

## Overview of the Project: 
<p align="justify">The project is to give investor a clear concept about the impact of weather in Oahu, Hawaii. Before investing to open the surf shop, specifically, investor wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round rather than a seasonal business.<p>
	
	
	
 
### <p align="justify"> Project features and resources<p>  
- Data source : hawaii.sqlite
- Programm File : SurfsUp_Challenge.ipynb
- Software : SQLlite, Python, Jupyter Notebook

 Surf-Analysis file(.ipynp) link -  [ Surf-Analysis](https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/tree/main/Queries)  

### <p align="justify"> Project deliverables<p>
-  Deliverable 1: Determine the Summary Statistics for June
-  Deliverable 2: Determine the Summary Statistics for December
-  Deliverable 3: A written report for the statistical analysis (README.md)
  
 
	

	
## Analysis Results: 
---
  
- <p align="justify"> The Summary statistics that filtered the date column of the Measurements table in the hawaii.sqlite database and retrieved all the temperatures for the month of June.<p>
  
  The Summary statistics for june :

  
<p align="center">
  <img width="600" src=https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/blob/main/resources/retirement_titles.png
</p>
	

	
  
- <p align="justify"> The Summary statistics that filtered the date column of the Measurements table in the hawaii.sqlite database and retrieved all the temperatures for the month of June.<p>
  
  The Summary statistics for December :

	<p align="center">
  <img width="600" src=https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/blob/main/resources/retirement_titles.png
</p>
		
		
 
  
Outcomes :
From the above scenarios, outcomes are observed: 
		
- The average temperature in June and December is about 75 degree F and 71 degree F respectively. i.e. 4 degree difference between months.
- June max temp 85 degree F and December max temp 83 degree F 
- June min temp 64 degree F and December max temp 56 degree F 

```sharif
  
--A Unique Titles table created that hold the most recent title of each employee excluding retired. (to remove duplicate rows, applied Dictinct ON employee_ID with Orderby )
	
SELECT DISTINCT ON (emp_no) 
		emp_no,
		first_name,
		last_name,
		title
INTO unique_titles
FROM retirement_titles
WHERE to_date ='9999-01-01'
ORDER BY emp_no, to_date DESC;
 
```     
    
    
## Summary:
<p align="justify">Several roles can be applied to make upcoming silver tsunami of the company in comfort zone. 
  
- <p align="justify"> The more older workers who retire early, the more vacant positions they leave. It can be eliminated by filling those positions with hiring experienced before leaving the old workers.</p>

- <p align="justify"> Train-up the existing employees as early as possible and step-up the position if required.</p>

- <p align="justify"> Hire retirees for part time basis so that they can train up those who need mentorship.</p>


<p align="justify"> There are enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees. By executing a query, we can show the member of mentorship group according to their recent title.</p>

  
```sharif
-- Statement for showing the Number of mentorship required employees by most recent Title.
SELECT 	COUNT(ti.title),
		ti.title
FROM employees as e
INNER JOIN titles as ti
ON (e.emp_no=ti.emp_no)
WHERE (e.birth_date BETWEEN '1965-01-01' AND '1965-12-31') and ti.to_date ='9999-01-01'
GROUP BY ti.title
ORDER BY COUNT DESC ;

```  
 
<p align="justify"> The query result of mentorship employees looks like:</p>
  
   
 <p align="center">
<img width="300" src=https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/blob/main/resources/mentorship_count.png
</p>
  
If we form a tabular view for the retiring_title count and mentorship group count by their title, we can observe the outcome clearly. 	
  
  <p align="center">


|Title                |Member of mentorship group  |Retiring Employees|
| :--------           |:---------:                  | --------: | 
| Senior Staff        | 569                       | 24926     | 
| Senior Engineer     | 529                       | 25916  | 
| Engineer            | 190                       | 9285     | 
| Staff               | 155                       | 7636     | 
| Technique Leader    | 77                        | 3603     | 
| Assistant Engineer  | 29                        | 1090     | 

</p>
  

 

<p align="justify"> If we focus on the above table, the total number of  employees need mentorship is 1549 where  senior staff is 569. Against them we have  24926 retiring senior staff, who can train them up. Number of Senior Engineer who need mentorship is 529. And we have 25916 retiring senior engineer to train them up. </p>

