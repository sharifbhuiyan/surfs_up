## **<h1 align="justify"> surfs_up**
Advance Data Storage and Retrieval with Jupyter Notebook, SQLite and SQLAlchemy.
	
---

## Overview of the Project: 
<p align="justify">The project is to give investor a clear concept about the impact of weather in Oahu, Hawaii. Before investing to open the surf shop, specifically, investor wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round rather than a seasonal business.<p>
	
	


<p align="justify">The project consists of two technical analysis.<p>
	
	
 
## <p align="justify"> Project features and resources<p>  
- Data source : hawaii.sqlite
- Programm File : SurfsUp_Challenge.ipynb
- Software : SQLlite, Python, Jupyter Notebook

 Surf-Analysis file(.ipynp) link -  [ Surf-Analysis](https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/tree/main/Queries)  

## <p align="justify"> Project deliverables<p>
-  Deliverable 1: Determine the Summary Statistics for June
-  Deliverable 2: Determine the Summary Statistics for December
-  Deliverable 3: A written report for the statistical analysis (README.md)
  
 
	
	
	
 ## Pewlett-Hackard-Analysis Results: 
  
- <p align="justify"> A table named ‘retirement_titles’ has been created filtering on the birth date who were born between 1952 and 1955. This table holds the list of employee’s status both existing and retired.<p>
  
  Retirement Title Table looks like :

  
<p align="center">
  <img width="600" src=https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/blob/main/resources/retirement_titles.png
</p>
	

	
  
- <p align="justify"> In ‘retirement_titles’ table, there are duplicate entries for some employees because of switched titles over the years. To remove these duplicates and keep only the most recent title of each employee, a unique_titles table has been created. This table holds the list of the most recent title of each employee who are not retired. A Distinct ON statement has been applied to remove duplicate employees filtering on ‘9999-01-01’.   
<p>

Statement for Unique Title Table :

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
  

    
- <p align="justify"> A retiring_titles table has been created that showing the number of retiring employees by most recent title. From this table, we could know that total number of retiring employees is 72458.   
<p>
  

Retiring Title Table looks like:
  
<p align="center">
  <img width="300" src=https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/blob/main/resources/retiring_titles.png
</p>



- <p align="justify"> A mentorship-eligibility table has been created that holds the current employees who were born between January 1, 1965 and December 31, 1965. The table shows that the total number of employees  required mentorship is 1549.
<p>
  
 
  
  
Mentorship eligibility Table looks like :

	
<p align="center">
<img width="600" src=https://github.com/sharifbhuiyan/Pewlett-Hackard-Analysis/blob/main/resources/mentorship_eligibilty.png
</p>

 
    
    
    
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

