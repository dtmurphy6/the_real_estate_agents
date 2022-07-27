# Project 2: The Real Estate Agents

## Team Members
Kevin Flores, Dan Murphy, Maite Rivas, Danielle Sears
## Project Description/Outline
We chose two datasets to extract, transform, and load. Our goal for this project is to assess housing prices around the country (United States) compared to the average salary for data scientists. Each dataset included a ton of information, so the main priorities were to analyze the columns within each dataset and find what we were actually interested in extracting data from. Moreover, we also had to decide what type of database to use so we chose on MongoDB, a NoSQL database. 

Below, we will describe how we extracted, transformed, and then loaded our original datasets as well as some findings.

## Extracting
For extraction, we used the [Redfin Real Estate Dataset 2012-2021](https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data) and [Data Scientist Salary Dataset](https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor), both from Kaggle. The zip file containing the Redfin Real Estate Data had multiple large files within it that were all formatted as TSV's, and each was a file for different types of housing data (i.e. nationwide, by state, by neighborhood, by county, and by zip code). We had to use Git LFS and add a .gitattributes to track our large files, but there were still two TSV files that were over 1 GB in size (neighborhood and zip code files) that we were unable to upload due to Git LFS restrictions. However, since all the housing datasets contained a large amount of information, we decided we were only interested in the US housing data by state anyway, so we chose the state file to use and then read the file into Pandas by specifing the '\t' separator. Luckily, the Data Scientist Salary file was already formatted as a CSV, it just needed to be read into the file using Pandas.

## Transforming
In order to transform our datasets, there were a few things to do. We started by checking for blank columns, and dropped columns from the files to exclude any unnecessary information. Next, the location column within the Data Scientist Salaries file had to be renamed so we could later join the two datasets on the state columns. We also decided we were only interested in Redfin Housing data from 2018 and on, since housing prices have changed so drastically in recent years. The chart contained information dating all the way back to 2012, and we felt 3 years worth of data would be enough information for our dataset or for future calculations. We did this by converting the date column and then getting housing data from those 3 years.

## Loading
Lastly, we had to store our information in a database, which we used mongoDB (non-relational) for, and then join the two databases on state.

# Questions to Answer:
What is the highest average salary by state?

What is the most common salary by state?

What is the highest/lowest price to buy a dwelling by state?

What is the highest differential between salary and price?

### What state has the highest average rating?
The states to live in with the highest median rating is Georgia, followed by Iowa, Minnesota, and South Carolina, and Alabama.

The states to live in with the highest mean rating is Minnesota, followed by Georgia, South Carolina, and Iowa, and Alabama.

## Sources of data
https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data

https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor


*See code [here](Code_Scripts/data_science_housing.ipynb)
