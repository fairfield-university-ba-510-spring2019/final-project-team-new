# Charles F. Dolan School of Business

# BA 510 – Final Project, SP 2019

## Team New

**Goal:** 
- The goal of this project was to Extract, translate, and load data into a normalized database
- Design and populate a  data warehouse designed to address our analytical questions
- Test your databases to ensure domain, entity, relational integrity

**Explanation of Work: Part 1) Database**
- We began by creating a normalized ERD for our DataBase:
![](CoursesDatabaseERD.png) 
[CoursesDatabaseERD](CoursesDatabaseERD.png)
  We also created a Data Dictionary for our ERD:
**[DataBaseDataDictionary](CourseDataDictionary.md)**

- We then built our database; we mainly used SQLITE3 but also used Pandas to read all the CSV files quickly and add a column explaining the catalog year.
**[Creating Database](CourseDataETL.ipynb)**

*Please note at the end of the file we delete all the tables and vacuum the database in order to allow us to commit to GitHub. Do not run this code if you want to query the database*

- We queried and tested our database using the following file
**[Testing Database](CourseDataTests.ipynb)**

 **Part 2) DataWarehouse**
 - We began by creating an ERD for our DataWarehouse:
![](CourseDataWarehouseERD.png) 
[CourseDataWarehouseERD](CourseDataWarehouseERD.png)
  We also created a Data Dictionary for our ERD:
**[DataWarehouseDataDictionary](CourseDataWarehouseDictionary.md)**

The Datawarehouse was designed to answer questions a new Dean may have about his/her new school. The Course_Facts table contains basic information while the dimensional  tables add extra information such as meeting times, location, additional fees and program data.

We began the Datawarehouse design by recreating the Database tables from our Database. We were unable to simply create a copy of the database.db file as this was too large for Jupyter Hub. Next, we created all the dimensional tables with surrogate primary keys. Creating and joining the Fact table provided challenging; we used the database tables to join the data and this allowed us to insert the primary keys from the dimensional tables in the fact table as foreign keys.
**[Creating DataWarehouse](CourseDataWarehouseETL.ipynb)**

In the future we would like to combine all class meeting times under a single MID, this would reduce some of the repetition we currently experience in our fact table.

