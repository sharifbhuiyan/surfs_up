## **<h1 align="justify"> surfs_up**
Advance Data Storage and Retrieval with Jupyter Notebook, SQLite and SQLAlchemy.
	
---

## Overview of the Project: 
<p align="justify">The project is to give investor a clear concept about the impact of weather in Oahu, Hawaii. Before investing to open the surf shop, specifically, investor wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round rather than a seasonal business.<p>
	
	
	
 
### <p align="justify"> Project features and resources<p>  
- Data source : hawaii.sqlite
- Programm File : SurfsUp_Challenge.ipynb
- Software : SQLlite, Python, Jupyter Notebook

 Surf-Analysis file(.ipynp) link -  [ Surf-Analysis](https://github.com/sharifbhuiyan/surfs_up/blob/main/SurfsUp_Challenge.ipynb)  

### <p align="justify"> Project deliverables<p>
-  Deliverable 1: Determine the Summary Statistics for June
-  Deliverable 2: Determine the Summary Statistics for December
-  Deliverable 3: A written report for the statistical analysis (README.md)
  
 
	

	
## Analysis Results: 
---
  
- <p align="justify"> The Summary statistics that filtered the date column of the Measurements table in the hawaii.sqlite database and retrieved all the temperatures for the month of June.<p>
  
  The Summary statistics for june :

  
<p align="center">
  <img width="250" src=https://github.com/sharifbhuiyan/surfs_up/blob/main/resources/june_summary.png
</p>
	

	
  
- <p align="justify"> The Summary statistics that filtered the date column of the Measurements table in the hawaii.sqlite database and retrieved all the temperatures for the month of December.<p>
  
  The Summary statistics for December :

<p align="center">
  <img width="250" src= https://github.com/sharifbhuiyan/surfs_up/blob/main/resources/dec_summary.png
</p>
		
		
 
  
**Outcomes :**
From the above scenarios, outcomes are observed: 
		
- The average temperature in June and December is about 75 degree F and 71 degree F respectively. i.e. 4 degree difference between months.
- June max temp 85 degree F and December max temp 83 degree F. 
- June min temp 64 degree F and December max temp 56 degree F. 

 
    
    
## Summary:
<p align="justify"> We can make final decision about our analysis by creating one summary by merging summary details of june and december. We can visualize those by histogram so that we can observe the outcome clearly. </p>  


  
```sharif
  
-- Merge the June and December temperature summary.
	
june_stats = june_df.describe()
dec_stats = dec_df.describe()

summary_df = june_stats.merge(dec_stats, left_index=True, right_index=True)
summary_df
 
```    
 
<p align="justify"> The query result of summary_df looks like:</p>
  
   
 <p align="center">
<img width="300" src=https://github.com/sharifbhuiyan/surfs_up/blob/main/resources/june_dec_comparison_summary.png
</p>
  
Histogram for the month of June and December : 
  
 <p align="center">
<img width="600" src=https://github.com/sharifbhuiyan/surfs_up/blob/main/resources/june_dec_comparison_plot.png
</p>

 

<p align="justify"> If we focus on the above histogram, I would say, even december temperature varied than june, still december weather condition is good enough for both surfing activities and demand of Ice-Cream. </p>

