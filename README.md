# Project 2: The Real Estate Agents

## Team Members:
Kevin Flores, Dan Murphy, Maite Rivas, Danielle Sears

## Project Description/Outline
We chose two datasets to extract, transform, and load. Our goal for this project is to assess housing prices around the country (United States) compared to the average salary for data scientists. Each dataset included a ton of information, so the main priorities were to analyze the columns within each dataset and find what we were actually interested in extracting data from. Moreover, we also had to decide what type of database to use so we chose on MongoDB, a NoSQL database. 

Below, we will describe how we extracted, transformed, and then loaded our original datasets as well as some findings.

## Extracting
For extraction, we used the [Redfin Real Estate Dataset 2012-2021](https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data) and [Data Scientist Salary Dataset](https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor), both from Kaggle. The zip file containing the Redfin Real Estate Data had multiple large files within it that were all formatted as TSV's, and each was a file for different types of housing data (i.e. nationwide, by state, by neighborhood, by county, and by zip code). We had to use Git LFS and add a .gitattributes to track our large files, but there were still two TSV files that were over 1 GB in size (neighborhood and zip code files) that we were unable to upload due to Git LFS restrictions. However, since all the housing datasets contained a large amount of information, we decided we were only interested in the US housing data by state anyway, so we chose the state file to use and then read the file into Pandas by specifing the '\t' separator. Luckily, the Data Scientist Salary file was already formatted as a CSV, it just needed to be read into the file using Pandas.

## Transforming
In order to transform our datasets, there were a few things to do. We started by checking for blank columns, and dropped columns from the files to exclude any unnecessary information. Next, some columns within the Data Scientist Salaries file had to be renamed so we could later join the two datasets on the state columns, and avoid issues by taking out any spaces in our columns, and took out any junior or senior roles to standardize our data. We also decided we were only interested in Redfin Housing data from 2019 and on, since housing prices have changed so drastically in recent years. The chart contained information dating all the way back to 2012, and we felt 3 years worth of data would be enough information for our dataset or for future calculations. We did this by converting the date column to date and time, and then getting housing data for those 3 years. 

From the Redfin State Housing Data, we chose to use: 'state', 'period_end', 'median_sale_price', 'median_ppsf', and 'property_type'. The Data Scientist Salary Data had a few different topics we were interested in, so we chose to use: 'state', 'rating', 'lower_salary', 'upper_salary', 'avg_salary', and 'job_title_sim'. We felt that these columns held the best information for future analysis and calculations, since they give us information about the job/housing location within the US, price ranges in properties and jobs, as well as property and job types to get better insight on the type of job or house. Lastly, we chose the rating of jobs to gain better background into the satisfaction of employees within their respective data science roles.

## Loading
In order to load our data, we had to store our information in a database, which we used mongoDB (non-relational) for. We started by creating our database name and then some smaller collections for our dataframes. We felt it would be useful to be able to look at information from datasets individually, so we made a collection for our Redfin Housing Data (2019 and on) and one for our Data Scientist Salary Data. This way, if a user needs to look at job or housing information individually, we have that information available. Next, we made a collection with both original datasets in case a user wants to look at the data together and compare housing costs to data science salaries, they can do that as well. Lastly, we also chose to have some collections for calculations such as mean and median to be able to provide users an overall look of the data by mean housing and salary, as well as by median housing and salary. 

## Questions to Answer:


### What is the highest/lowest price to buy a dwelling by state?

The lowest housing cost was in Alabama, followed by Mississippi, West Virginia, Michigan, and Maryland.

The highest housing cost was in Hawaii, followed by Connecticut, New Mexico, Washington, D.C., and Maine.


### What state has the highest average rating?

The states to live in with the highest median rating is Georgia, followed by Iowa, Minnesota, and South Carolina, and Alabama.

The states to live in with the highest mean rating is Minnesota, followed by Georgia, South Carolina, and Iowa, and Alabama.



### What is the highest average salary by state?

### What is the most common salary by state?

### What is the highest differential between salary and price?



## Sources of data
https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data

https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor


*See code [here](Code_Scripts/data_science_housing.ipynb)
