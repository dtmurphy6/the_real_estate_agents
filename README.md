# Project Title: The Real Estate Agents

## Team Members
Kevin Flores, Dan Murphy, Maite Rivas, Danielle Sears

## Project Description/Outline
We chose two datasets to extract, transform, and load. Our goal for this project is to assess housing prices around the country (United States) compared to the average salary for data scientists. Each dataset included a ton of information, so the main priorities were to analyze the columns within each dataset and find what we were actually interested in extracting data from. Moreover, we also had to decide what type of database to use so we landed on MongoDB, a NoSQL database. Below will describe how we extracted, transformed, and then loaded our original datasets.

## Extracting
We are using the Redfin Real Esate Data and Data Scientist Salary Data from [Kaggle](https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data). The file with the Redfin Real Estate Data is formatted as a TSV with multiple files for different types of housing data (i.e. nationwide, statewide, by neighborhood, etc), so we isolated the necessary data and converted it to a CSV. The Data Scientist file is already formatted as a CSV file, but its location data needed to split up so we can get state and city into individual columns and later join them by the state columns.

## Transform
We adjusted the datasets so that the columns can more easily be joined. We also checked for blank columns and dropped columns from the files to exclude any irrelevant or unnecessary information.

## Load
We plan on storing our information in mongoDB (non-relational) and joining our two databases on city/state.

# Questions to Answer:
What is the highest average salary by state?

What is the most common salary by state?

What is the highest/lowest price to buy a dwelling by state?

What is the highest differential between salary and price?

### What state has the highest average rating?
The states to live in with the highest median rating is Georgia, followed by Iowa, Minnesota, and South Carolina, and Alabama.

The states to live in with the highest mean rating is Minnesota, followed by Georgia, South Carolina, and Iowa, and Alabama.

# Sources of data

https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data

https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor
