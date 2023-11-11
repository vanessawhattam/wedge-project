# Applied Data Analytics

## Wedge Project

This project is an ETL pipeline for data from the Wedge, a Minneapolis-based co-op grocery store. There are transaction files from 2010-01-01 through 2017-01-31 stored as *.csv files, which are processed and loaded to a Google Big Query project. After the files are loaded, they are queried and used to build additional tables to support business operations. 

<!-- Any general commentary you'd like to say about the project --> 

### Task 1

* Files for this task: 
<!--  List of file or files here  --> 
`task1_upload.ipynb`: This file contains the code for processing the Wedge zip files, including changing delimiters to ",", adding a header to files where it is missing, and modifying missing/null values so that they are recognized as `NULL`. There is also a cell that extracts each of the *.csv files from their zipped folders and places them into a folder call wedge_extracts. Finally, each of the *.csv files are uploaded to Google Big Query via a pandas dataframe passthrough. 


`task1_testing.ipynb`: This file contains the code to determine which Wedge *.csv files contain ";" as a delimiter and which lack a header so that we can process through them in `task1_upload.ipynb` and save a little time because we don't have to go through every single one. This code also puts the files that need cleaning into specific folders.

<!--  Repeat for each file  --> 


### Task 2

* Files for this task: 
<!--  List of file or files here  --> 

`task2.ipynb`: This file contains Python code that creates a SQL query, queries the pre-cleaned Wedge files, and creates a sample of the complete records of 420 unique Wedge owners.

<!--  Repeat for each file  --> 
	

### Task 3

* Files for this task: 
<!--  List of file or files here  --> 

`task3.ipynb`: This jupyter notebook first creates a SQLite database called wedge_data2. It then sends a query to Google Big Query, writes the results to a dataframe, then creates a SQLite table from the dataframe for three different queries. 

<!--  Repeat for each file  --> 


## Query Comparison Results

Fill in the following table with the results from the 
queries contained in `gbq_assessment_query.sql`. You only
need to fill in relative difference on the rows where it applies. 
When calculating relative difference, use the formula 
` (your_results - john_results)/john_results)`. 



|  Query  |  Your Results  |  John's Results | Difference | Rel. Diff | 
|---|---|---|---|---|
| Total Rows  | 85,760,139  | 85,760,139  | 0  | 0  |
| January 2012 Rows  | 1,070,907  | 1,070,907  | 0  | 0  |
| October 2012 Rows  | 1,042,287  | 1,042,287  | 0  | 0  |
| Month with Fewest  | February  | February  | Yes  | NA  |
| Num Rows in Month with Fewest  | 6,556,770  | 6,556,770  | 0  | 0  |
| Month with Most  | May  | May  | Yes  | NA  |
| Num Rows in Month with Most  | 7,578,372  | 7,578,372  | 0  | 0  |
| Null_TS  |  7,123,781 | 7,123,792  | 11  | <0.0001  |
| Null_DT  | 0  | 0  | 0  | 0  |
| Null_Local  | 234,839  | 234,843  | 4  | <0.0001  |
| Null_CN  | 0  | 0  | 0  | 0  |
| Num 5 on High Volume Cards  | 14987  | 14987  | Yes  | NA  |
|  Num Rows for Number 5 |  460,625 | 460,630  | 5  | <0.0001  |
| Num Rows for 18736  |  12,153 | 12,153  | 0  | 0  |
| Product with Most Rows  | banana organic  | banana organic  | Yes  | NA  |
| Num Rows for that Product  | 908,639  | 908,639  | 0  | 0  |
| Product with Fourth-Most Rows  | avocado hass organic  | avocado hass organic  | Yes  | NA  |
| Num Rows for that Product  | 456,771  | 456,771  | 0  | 0  |
| Num Single Record Products  | 2741  | 2769  | 28  | 0.01  |
| Year with Highest Portion of Owner Rows  |  2014 | 2014  | Yes  | NA |
| Fraction of Rows from Owners in that Year  | .7591  | .7591  | 0  | 0  |
| Year with Lowest Portion of Owner Rows  | 2011  | 2011  | Yes  | NA |
| Fraction of Rows from Owners in that Year  | .7372  | .7372  | 0  | 0  |

## Reflections

Overall, this project taught me that I am firmly on the analysis side of data science. While I would much rather be running models off of the data, I did feel that my Python skills improved throughout this project and I could more easily translate the concepts from my head to the code. This was a good challenge and a little frustrating – I probably uploaded all of my tables to GBQ at least 10 different times throughout the project because I would discover little errors. I felt like the concepts learned were applicable to real-life applications. My code is definitely not idempotent, but it got me from A to B (and hopefully to an A).

<!-- I'd love to get 100-200 words on your experience doing the Wedge Project --> 
