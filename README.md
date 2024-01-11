# Aryonna Rice's Portfolio
## Table of Contents

1. [About Me](#about-me)
2. [What I Do Best] (#what-i-do-best)
3. [Skills](#skills)
4. [Projects](#projects)
5. [Contact Information](#contact-information)

## About Me
Hi! I'm Aryonna, a passionate senior computer science student at the University of North Carolina at Chapel Hill with a flair for backend development. My expertise lies in crafting robust solutions using Python and Java. Proficient in SQL ORM, SQL CORE, and MS SQL, I delve into the intricacies of databases with ease. I am a problem solver and love a good challenge!

## What I Do Best
I thrive on problem-solving and enjoy the creative process of designing efficient solutions. Whether it's untangling complex coding challenges or engineering seamless backend systems, I'm in my element when transforming problems into elegant solutions.

## Skills
1. Python - Fluent
2. Java - Fluent
3. Lisp - Knowledgable
4. ML - Knowledgable
5. Prolog - Knowledgable
6. SQL – Knowledgeable
7. MS SQL – Knowledgeable
8. PostgreSQL – Knowledgeable
9. SQL ORM – Knowledgeable
10. Google Certified Associate Cloud Engineer
    
## Projects
1. Saving data to an MS SQL database
   
   - Task: Save data from a Pandas dataframe into a preexisting table in the company's MS SQL database in long and JSON format.
   - Problem: Prior to my undertaking of the project, there was no interim table for data to be stored in one of the company's databases. The table my boss wanted me to create served as temporary storage for data (before it was saved to more specific tables). Overall, data from different dataframes would be saved in this table temporarily.
   - Requirements / Criteria:
       - Remove all special characters and spaces from column names
       - Save data under *new* column names (col_name, col_val, data, etc)
       - Dataframes with less than 1 million rows must all be inserted in under 60 seconds
   - Walk-through: The data to be inserted into the temporary table is originally held in a Pandas dataframe and looks something like this. The data would look like this in the long format table in the MS SQL database and would look like this if saved in the JSON format table.
   - Skills learned:
        - Setting up a connection with a database
        - Pandas:
            - to_sql, melt, pivot, merge, concat, etc
        - SQL:
            - Writing raw queries
            - Injection attack-proof queries 
    - Python code:
        - Created data-cleaning functions
        - Utilized regular expressions
        - Utilized concurrency (ThreadPoolExecutor) to insert data in batches
- Results:
    - Long format:
        - Saved ~840,000 rows of data in 53.87 seconds
    - JSON format:
        - Saved ~11,800 rows of data in 12.34 seconds
    - Team adopted my code into production
    - Offered a full-time position post-grad


## Contact Information
- Email: aryonnarice@unc.edu
- LinkedIn: https://www.linkedin.com/in/aryonna-rice/

