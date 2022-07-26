## the_real_estate_agents
# Project Title 
The Real Estate Agents

# Team Members
Dan, Danielle, Kevin, Maite

# Project Description/Outline
The goal of this project is to assess housing prices around the country (United States) compared to the average salary for data scientists. 

# Extract
We are using the Redfin Real Esate Data and Data Scientist Salary Data from Kaggle. The file with the Redfin Real Estate Data is formatted as a TSV with multiple files for different types of housing data (i.e. nationwide, statewide, by neighborhood, etc), so we isolated the necessary data and converted it to a CSV. The Data Scientist file is already formatted as a CSV file, but its location data needed to split up so we can get state and city into individual columns and later join them by the state columns.

# Transform
We adjusted the datasets so that the columns can more easily be joined. We also checked for blank columns and dropped columns from the files to exclude any irrelevant or unnecessary information.

# Load
We plan on storing our information in mongoDB (non-relational) and joining our two databases on city/state.

# Question to Answer
What is the highest average salary by state?

What is the most common salary by state?

What is the highest/lowest price to buy a dwelling by state?

What is the highest differential between salary and price?

What is the highest rated data science position in the US?

What state has the highest average rating?

# Sources of data

https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data

https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor
