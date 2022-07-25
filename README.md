## the_real_estate_agents
# Project Title 
The Real Estate Agents

# Team Members
Dan, Danielle, Kevin, Maite

# Project Description/Outline
The goal of this project is to assess housing prices around the country (United States) compared to the average salary for data scientists. 

# Extract
We plan on using Redfin real esate data and Data scientist salary data from Kaggle. The file with the Redfin real estate data is formatted as a TSV with multiple files for different types of housing data (i.e. nationwide, statewide, by neighborhood, etc), so we had to figure out what data we wanted to use from it and convert it to a CSV. The Data Scientist file is already formatted as a CSV file, but its location data needs to be split up so we can get state and city into individual columns and later join them by the state columns.

# Transform
We will need to adjust the datasets so that they columns can more easily be joined. We will need to check for blank columns or other data that needs to be cleaned.

# Load
We plan on storing our information in mongoDB (non-relational) and joining our two databases on city/state.

# Question to Answer
What is the highest average salary by state?

What is the most common salary by state?

What is the highest/lowest price to buy a dwelling by state?

What is the highest differential between salary and price?

What is the highest rated data science position in the US?

What state has the highest average rating?

What state has the highest average square footage?

What is the most common square footage by state?

# Sources of data

https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data

https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor
