# Data-Analytics-Week-2
_Exploring Databases:_
- There are different database option to choose when storing data, thus belong in of two categories, which is:
                  1. Relational
                  2. Non-relational
- Relational databases is one of the oldest and most mature databases and, they store and process structured data acceptionally.
- Nonrelational databases's factor is that there is a need to interact with unstructured data.
- Many of the systems we interact with daily produce tabular data, and this is because tabular data is structured.

_Relational Model:_
- The relational model for database management of IBM was developed by Edgar F.Codd in 1969.
- Relational model builds on the concept of tabular data and contains data for a single subject.
- When you create an IT system, entities needed to make the system need to be consider. Entities usually correspond to people, place, and things(thus are nouns).
- An entity instance identifies as specific example of an entity. So, for example, there is an animal entity and an entity instance is a particular animal.
- The entity's name is the bolded word in the header.
- The header of the table entity corresponds to the name of the entity.
- Every row represents an individual attribute associated with that entity.
- Every entity becomes a seperate table in the database, with a column for each attribute.
- Each row represents an instance of the entity.
- Relational models allows us to describe how entities connect or relate to each other.
- There is a visual artifact of the modeling process, and we can go about it by implementing the entity relationship diagram (ERD).
- We show the relationship through a connection represented by a line.
- The relationship between two entities, that shows how many instances of one entity relating to instances in another entity is refered to a cardinality.
- You specify cardinality in an ERD with various line endings.
- The figure below shows the possible combinations for representing relationships:

- We have unary relationship which is when an entity has a connection with itself.
- We have a binary relationship which connects two entities and tenart which only connects three entities.
- Binary relationship are more common and easy to explore. Unary and tenary are complex and rare.
- To be able to read ERDs helps one to understand the structure of relational database.
- ERDs are useful to formulate how to retrieve information from the database that is spread across multiple tables.
- This is because the diagrams allow us to visualise the connections between entitites.

_Relational Databases:_
- Relational databases: pieces of software that let you make an operational system out of an ERD.
- You start with a relational model and then create a physical design.
- Relational entities - correspond to database tables, and entity attrivutes - correspond to table columns.
- The ordering of columns does not matter when you create a database. This is because you can specify the column order when retrieving data from a table.
- Assign it a data type when an attribute becomes a cloumn.
- When all is done, the results are displayed in a diagram, known as a schema which is an ERD with added details needed to create a database.

_Nonrelational Databases:_
- Does not have a predefined structure based on tabular data.
- Examples of nonrelational databases include
              - key-value - one of the simple ways to store data and data is stored as a collection of keys and their corresponding values,
              - document - similar to key-values but have additional restrictions. Value is restricted to a specific structure format,
              - column family - use an index to identify data in groups of related columns,
              - and graph - specialise in exploring relationships between pieces of data.
- 

_Database Use Cases:_
- Different business needs require different database designs, whereas all databases store data, the database's structure needs to match its indeded purpose.

_Online Transactional Processing:_
- OLTP systems handle the transactions we encouter every day.
- Eg, transactions include booking a flight reservation, ordering something online, or executing a stock trade.
- Even though the number of transactions a system handles on a given day can be high, individual transactions process small amounts of data.
- OLTP systems balance the ability to read and write efficiently.

_Normalization:_
- Normalization: a process for structuring a database in way that minimizes duplication of data.
- One of the principles is that given a piece of data is stored once and only once.
- A normalized database is ideal for processing transactions.
- First normal form (1NF): when every row in a table is unique and every column contains a unique value.
- Second normal form (2NF): starts where 1NF leaves off. To add on, each row being unique, 2NF applies an additional rule stating that all nonprimary key values must depend onf the entire primary key.
- Third normal form (3NF): builds upon 2NF by adding a rule stating all comlumns must depend on only the primary key.

_Online Analytical Processing:_
- OLAP systems focus on the ability of organization to analyse data.
- OLAP and OLTP databases both use relational database technology, however their structures are fundamentally different.
- In such that OLTP databases need to balance read and write peformance which results in a highly normalised design. They are in 3NF.
- Databases that power OLAP systems have a denormalised design.
- Instead of having data distrubuted across multiple tables, denormalisation results in wider tables than those found in an OLTP database.
- It is more efficient for analytical queries to read large amounts of data for a single table instead of incurring the cost of joining multiple tables together.

_Schema Concepts:_
- The design of a databse schema depends on the purpose it serves.
- Transactional systems need highly normalised databases, whereas a denormalised design is more appropriate for analytical systems.
- A data warehouse is a database that is a collection of data from many transanctional systems for analytical purposes.
- Transactional data come from systems that power the human resources, sales, marketing, and product divisions.
- A data warehouse it makes it easier for analytics across the entire company.
- Data mart: a subset of a data warehouse. Data warehouses serve the entire organisation, whereby data marts focus on the needs of a particular department within the organisation.
- Data lake: stores raw data in its native format instead of conforming to a relational database structure.
- It is important to establish that the structure of a database schema impacts analytical efficiency, mainly as the volume of data grows.
- It is important to consider the life-cycle. Life-cycle considerations include where data comes from, how frequently it changes, and how long it needs to persist.
- We have two types of schema design:
            - Star: facilitate analytical processing get its name from what the schema looks like when                        looking at its entity relationship. Are denormalised to improve read performance                         over large datasets. We usually have a fact table at the centre of star, and its                         purpose is to store numerical facts about a business.
            - Snowflake: dimensions have subcategories, which gives the snowflake design its shape. It                            is less denormalised than the star schema.
- The amount of storage a database needs decreases as a function of the degree of normalisation. OLTP - highly normalised, OLAP - denormalised.

_Dimensionality:_
- Dimensionality: number of attributes a table has. Greater the number of attributes, the higher the dimensionality/
- Dimension table provides additional context around data in fact tables.
- It is important to understand the types of question an analyst will need to answer when designing dimension tables.
- One dimension you will encounter is time, you need to answer quesions about when something happened or when something is true.
- To accomplish this is to add a start and end date of each product's price.
- Consider a geographic dimension which changes over time.

_Handling Dimensionality:_
- 

_Data Acquisition Concepts:_
- To perform analytics, data is needed. Data can come form internal systems you operate, or you can obtain it from third-part sources.
- You need to get data before analysing it to derive additional value.

_Integration:_
- Data from transactional systems flow into data warehouses and data marts for analysis.
- Retrieve, reshape, and insert data to move dara between operational and analytical environments.
- There is a variety of methods to transfer data efficiently and effectively, and one way is know as extract, transform, and load (ETL).
- This method consists of three phases:
            1. Extract: first phase - extract data from the source system and place it in a staging area. Goal is to move data from a relational database into a flat file as quickly as possible.
            2. Transform: second phase - transforms data. Goal is to refromat the data from its transactional structure to the data warehouse's analytical design.
            3. Load: purpose of this phase is to ensure data gets into analytical system as quickly as possible.
- With ELT (extract, load, and transform), a variant of ETL, data is extracted from a source database and loaded directly into the data warehouse.
- Once the extract and load phases are complete, the transformation phase gets moving.
- Difference between ELT and ETL is the technical component performing the transformation.
- ETL's data transformations takes place external to a relational database, they use programme language like Python.
- ELT uses SQL and the power of a relational database to reformat the data.
- ELT advantage - speed with data moving from the operational to the analytical database.
- ELT is beneficial when the data warehouse has a lot of capacity.

_ETL Vendors:_
- Most products support both ETL and ELT.
- If you want to pick one. evaluate the available free and paid options to establish the best fits your needs and system architecture goals.
- Initial load shows the first time data is put into a data warehouse.
- After initial load, each additional load is delta load, which is known as an incremental load.
- Delta load - moves changes between systems.
- Initial load happens before data warehouse becomes avaialable for use.
- Delta interval can happen at any time depending on how fresh the data needs to be.
- Balance speed and complexity of the overall operation when you move data between systems.
- Need to be aware of the time avaialble for performing delta loads int your data warehouse.
- Regardless of how long your batch window is, understand moving current data into the data warehouse without losing history.

_Data Collection Methods:_
- A good way to improve analytical capabilities in an organisation is to implement augmenting data from transactional systems with external data.
- A good way to improve your business is through internal data.
- Improving accurancy of your analysis, you include data about weather, tourism, and your competitors.
- This additional data can come from various sources.
- With this, we will have:
          - Application Programming Interfaces(APIs): structured method to exhange information for computers
          - Web Services: an API you can call via Hypertext Transfer Protocol(HTTP)
          - Web Scraping: programmatic retrival of data
          - Human-in-the-Loop
          - Surveys: way to collect data directly from customers is by conducting a survey
          - Survey Tools: powerful tool for developing and administrating surveys is qualtrics
          - Observation: act of collecting primary source data, from either machines or people.
          - Sampling

_Working With Data:_
- To turn a database design into an operational database ready to acceot data, you use the Data Definition Language(DDL) components of SQL.
- DDL allows you to creat, modify, and delete tables and other associated database objects.
- A productive analyst use Data Manipulation Languagae (DML) capabilities of SQL to get generate insights. SQL inserts, modify and retrieve information from databases.
- DDL - manages the structure of a database, DML - manages the data in the database.

_Data Manipulation:_
- These are four ways to manipulate:
          1. Create new data 
          2. Read exisiting data
          3. Update existing data
          4. Delete existing data
- DML verbs are known as keywords or words that are paaart pf the SQL language itself.
- The operation below shows the SQL Keyword and description.
- Create - INSERT - creates a new data in an existing table
- Read - SELECT - retrives data
- Update - UPDATE - changes existing data
- Delete - DELETE - removes existing data
- SELECT, FROM, and WHERE are all reserved words specific meanings in SQL.
- SELECT - identifies the columns from the table(s) that are retrieved. Eg, SELECT Animal_Name, Breed_Name.
- FROM - identifies the source data, which is from the database table.
- Both SELECT and FROM are required for a SQL statement to return data as follows:
                - SELECT Animal_Name, Breed_Name
                - FROM Animal

_SQL CONSIDERATIONS:_
- SQL keywords are case-insensitive. But, the case-sensitivity of column names and values depend on the database configuration.

# DATA QUALITY CHALLANGES
- Analysts often analyze data in data warehouses, but each source has unique quality issues that need resolution.
- Before analyzing, analysts must examine each data source and resolve any underlying issues, such as cleaning and profiling datasets for various reasons.

_Duplicate Data:_
- Duplicate data occurs when data from the same transaction is accidentally duplicated within a system.
- This can occur when users double-click on a file or when multiple data sources for the same data elements are used.
- System architects work to prevent duplicate data creation by implementing visual warnings to alert users.
- To resolve duplicate data issues, companies have a duplicate resolution process that checks for customers with multiple billing addresses, validates the correct address, and updates the Sales database by removing the duplicate record.
- This helps prevent the creation of duplicate data and ensures accurate and efficient system operations.

_Redundant Data:_
- Data redundancy occurs when the same data elements exist in multiple places within a system, often due to integrating multiple systems.
- This is because shared data elements in different systems can cause conflicting values across systems.
- For example, a Sales ETL Job copies data from the Sales database into the Warehouse, while the Accounting ETL Job copies accounting data into the Warehouse.
- This creates a potential data redundancy problem, as different systems have different addresses for the same customer.
- Resolving redundant data involves synchronizing changes to shared data elements between the Accounting and Sales systems, but technical or political realities can make this impossible.
- The integrated ETL process uses a delta load approach to update addresses and ensure correct warehouse values.
- This helps resolve data discrepancies between Sales and Accounting systems.
- Inappropriate database design, such as billing by the hour, can also cause data redundancy.

_Missing Values:_
- Missing values, also known as null values, are issues that affect data quality.
- Null values are the absence of a value, not a space or blank. While some situations allow for null values, such as in a Middle Initial column, they can pose calculation challenges.
- For example, a temperature sensor's temperature column might have a null value for January 4, 2020, causing an error. Null values can be problematic depending on the data analysis tools used. SQL offers functions to check for null values and replace them with a user-specified value, while Python and R offer similar functions.

_Invalid Data:_
- Invalid data refers to values outside the valid range for a given attribute, violating business rules rather than having incorrect data types.
- Understanding the context of a system is crucial to determine if a value is invalid.
- For example, a temperature sensor with a date data type and a numeric temperature column is invalid if it is an unrealistic number.
- Programming languages lack native functions to determine invalid values, so data professionals must work with software developers to create rules based on their organization's unique needs.
- Invalid values violate business rules, not technical ones.
- Data professionals should work with software developers to create rules based on their organization's unique needs.
- Numeric and date data are easier to check for invalid values, while text data is more complex and can be invalid due to lack of referential integrity.

_Nonparametric Data:_
- Nonparametric data is collected from categorical variables, which can indicate differentiation or rank order.
- The rank order of the values is of significance, not the individual values themselves.
- For example, a person with abdominal pain may rate their pain on a scale of 0 to 10, which helps put their discomfort in context.
- If the person answers 8 on the scale, it equates to severe pain, and the doctor might order an X-ray or ultrasound to inform treatment options.

_Data Outliers:_
- A data outlier is a value that significantly differs from other observations in a dataset.
- For example, in a real estate sale price example, the property at 130 Main Street has a sale price of $26,496,400, which is significantly higher than the rest.
- Understanding outliers is crucial for analyzing data.
-  For example, if the property is a commercial property, it should be removed from the dataset for residential real estate prices analysis. If it's not a commercial property, a data entry error may have created the outlier, requiring correction. Outliers exist regardless of data type.

_Specification Mismatch:_
- A specification is a document that outlines the target value for a component, and a specification mismatch occurs when an individual component's characteristics are beyond acceptable values.
- For example, if a wooden stud is purchased with a rectangular cross-section, it may not match the blueprint. To avoid complications, the board is replaced with a 2x4. In manufacturing, a specification mismatch can cause a component to fail post-production quality checks.
- Understanding a specification's tolerance is crucial for maintaining quality. Invalid data has values that fall outside a given range.
- A specification mismatch can also occur when data does not conform to its destination data type.
- To resolve this mismatch, it is necessary to validate that the inbound data consistently maps to its target data type.

_Data Type Validation:_
- Data type validation ensures consistent data types in datasets.
- The load process handles data type validation failures, affecting the successful loading of remaining rows.
- Programming languages like SQL, Python, and R have data type validation functions.
- Detecting and resolving issues early is crucial for data readiness for analysis.
- Depending on the tool, a single failure may cause the process to stop or write each failed record to an error file.

# Data Manipulation Techniques
- This section discusses various potential data quality issues and discusses various data manipulation techniques to address these concerns.

_Recoding Data:_
- Recoding data is a method that maps original values of a variable into new ones for analysis.
- It groups data into multiple categories, creating a categorical variable. Categorical variables can be nominal or ordinal, with no natural order or inherent rank. Recoding is useful when analyzing numeric data by category.
- For example, if a hospital administrator needs to determine the number of people reporting moderate pain according to a pain scale, they can recode the numeric data and create a categorical variable.
- This process can be implemented regardless of the programming language used. The Pain_Category column is created, and the administrator can now understand that two people reported moderate pain.

_Derived Variables:_
- A derived variable is a new variable created from a calculation on an existing variable.
- It can be categorical or not.
- For example, a patient's age is a function of the current date, not the date of birth. To avoid potential age-related data errors, it is better to embed the formula to derive age in code, ensuring the value is obtained exactly when needed, rather than keeping it as a derived column.

_Data Merge:_
- A data merge is a process that combines multiple datasets with different structures into a single dataset, improving data quality by adding new variables.
- This process is commonly used in Enterprise Resource Planning (ERP) processes to transform data for analytical environments.
- By adding columns to a dataset, merging provides additional data about a specific observation.
- For example, to obtain an overall picture of a person's health, one might merge records from their primary care physician, self-reported dietary and exercise habits, and other sources of data.
- This would result in a table with additional columns, augmenting the amount of data about each person in the population. This data append is part of the ETL process, facilitating advanced analytical techniques.

_Data Blending:_
- Data blending is a process that combines multiple data sources into a single dataset at the reporting layer.
- It differs from Extract, Transform, and Load (ETL) in that it allows analysts to combine datasets ad hoc without saving them in a relational database.
- The blended dataset exists only at the reporting layer, not in the source databases.
- Data visualization tools like Tableau allow analysts to connect to different source systems and blend the data using a shared attribute.
- Data blending can reduce IT burdens by allowing analysts to merge data. However, the level of knowledge required for productivity is crucial.
- ETL processes are programmatic and operate on a schedule, resulting in a merged dataset that persists at the data layer.
- Data blending connects data at the visualization layer, allowing analysts to integrate additional data sources in an ad hoc, exploratory manner.

_Concatention:_
- Concatenation is the merging of separate variables into a single variable, which is useful in dealing with source systems that store components of a single variable in multiple columns.
- It is particularly useful when dealing with date and time data, generating address information, or aggregating temperature sensor data for analysis tools.
- Programming languages like SQL, Python, and R have functions that make concatenation easy, making it a straightforward activity to combine data in various applications.

_Data Append:_
- A data append is a process where multiple data sources with the same structure are combined to create a new dataset.
- This process is used for ongoing analysis, such as in meteorology or franchising.
- The National Weather Service (NWS) provides data from multiple weather stations, which are then appended by the NWS server. This data is then used to base forecasts.
- For example, a franchisor with multiple franchisee locations can use the same point of sales system to aggregate sales analysis, appending data from each franchise into a single table for ongoing analysis.

_Imputation:_
- Imputation is a technique used to replace missing values in data from multiple sources, such as sensor data.
- It can be caused by various reasons, such as lost network connections, manual scale use, or inability to record values. To handle missing data, analysts can use various approaches:
      - Remove Missing Data: This method removes rows with missing values without       affecting the overall analysis. Replace with Zero: This method replaces           missing values with a zero, which is not appropriate as a person's weight         should be a positive number.
      - Replace with Overall Average: This method computes the average weight             value for all rows with data and replaces missing values with that.
      - Replace with Most Frequent (Mode): This method uses the most frequently           occurring value as a constant.
      - Closest Value Average: This method uses the values from the rows before           and after missing values, like 2/13/2021 and 2/14/2021.

_Reduction:_
- Reduction is a method used to shrink a large dataset without affecting its analytical value.
- There are various techniques available, including dimensionality and numerosity reduction, depending on the type of data and the analysis objectives.
- These techniques are often inefficient and unfeasible when dealing with big data.

_Dimensionality Reduction:_
- Dimensionality reduction is a technique that reduces the size of a dataset by removing attributes.

_Numerosity Reduction:_
- Numerosity reduction is a technique that reduces the overall volume of data, especially when dealing with large datasets.
- For example, a decade's worth of Weight Log data can represent 3,650 individual data points per person, which can be overwhelming for a laptop or desktop. To improve efficiency, numerosity reduction can be used.
- Creating a histogram, a diagram made up of rectangles or bars, can help reduce the volume of quantitative data. Histograms can be created in Python, R, and visualization-specific tools, and can be used to represent a range of values.
- Regardless of the number of data points, both histograms convey the number of times each weight occurs in the data.
- Sampling is another approach to reducing data, selecting a subset of individual records from the initial dataset.
- The most straightforward technique is a random sample, which can be used in many cases.
- The time to produce these diagrams varies, with a standard laptop processing the entire dataset in about 45 seconds, while creating a sample-based histogram takes only 0.2 seconds.
- Sampling is a common approach for improving analyst efficiency as data volumes increase:
              1.Aggregation: Data aggregation is the summarization of raw data for analysis.
              2. Transposition: Transposing data is when you want to turn rows into columns or columns into rows to facilitate analysis
              3. Normalization: Normalizing data differs from our discussion of database normalization
              4. Min-Max Normalization
              5. Parsing/String Manipulation


# Managing Data Quality
- To enhance data quality, analysts must identify scenarios that trigger issues and create a mental checklist by exploring different situations and examining the application of different data quality controls.

_Circumstances to Check for Quality:_
- Implementing data quality control checks is crucial throughout the data life-cycle journey, as errors during acquisition, transformation, manipulation, and visualization can degrade data quality.
- Recognizing potential quality issues and having a comprehensive strategy is essential for ensuring data quality.
- We ensure it the following:
            1. Data Acquisiton
            2. Data Transformation and Conversion
            3. Data Manipulation
            4. Final Product Preparation

_Aumotated Validation:_
- Analytics environments often rely on various data sources, including computer systems and human-generated ones.
- Data entry mistakes can negatively impact data quality, so automating data validation checks can help.
- Understanding how source data fields map to their corresponding database columns is crucial.
- Paying attention to data types in the database can prevent errors.
- For instance, if a web form allows free text entry, automating data type validation before passing data to the database can prevent data type mismatches.
- Similarly, verifying the number of data points can help identify sensor failures early, preventing missing data from flowing into the analytics environment.
- Automating these checks can help maintain data quality and prevent data entry errors.

_Data Quality Dimensions:_
- To improve data quality, it's crucial to consider six dimensions: accuracy, completeness, consistency, timeliness, uniqueness, and validity.
- Understanding these dimensions and their relationships can enhance data quality, thereby enhancing overall data quality.
- These are each dimensions:
            1. Data Accuracy
            2. Data Completeness
            3. Data Consistency
            4. Data Timeliness
            5. Data Uniqueness
            6. Data Validity

_Data Quality Rules and Metrics:_
- Data quality dimensions, including data conformity, accuracy, consistency, uniqueness, and validity, are crucial for improving overall quality. Nonconformity occurs when source data does not match the destination data type size and format.
- For instance, the Warehouse Load ETL (ETL) job needs to ensure consistency when propagating data from different source systems into the Data Warehouse.
- Nonconformity can be addressed by confirming the number of successful rows and the number of failed rows.
- For example, if a customer has an 11-character last name, the ETL job needs to copy the bill details but not the last name field when loading the Data Warehouse.
- This creates a data quality issue in the Data Warehouse.
- To validate data conformity issues, confirm the number of successful rows and the number of failed rows.
- For example, if 900,000 rows are successful, the Warehouse Load ETL job sends 100,000 nonconforming rows to a Bad Data staging area.
- A data engineer resolves the root cause of the data quality issue before sending the remediated data into the Data Warehouse. This approach makes efficient use of resources and improves quality.

_Methods to Validate Quality:_
- Various methods are available to validate data quality, including assessing data accuracy and identifying irregular patterns.
- A effective approach is to combine these methods effectively.
- Reasonable Expections: To ensure data quality in your analytics environment, it's crucial to assess if the data meets your reasonable expectations. For instance, if your transactional systems process 10 million records daily, you should expect 300 million records by 30 days. If only 20 million are seen, it's likely that the data propagation ETL is failing. To automate this, create exception reports in your ETL processes. If successful rows are less than attempted rows, internal alarms should be raised, and the root cause of the ETL load failure should be addressed.
- Data Profiling: Data profiling is a method to enhance data quality by identifying discrepancies, irregular patterns, and missing values. It can help analyze customer engagement by examining the frequency of customer logins. For instance, a customer might log in three hundred times per day from three hundred unique devices, originating from multiple locations. This data fails the reasonable expectation test, as customers typically log in less frequently and from fewer devices. Therefore, it's crucial to investigate the data's authenticity rather than trusting it.
- Data Audits: Data audits are crucial for businesses to ensure they have the necessary data for operations. They use data profiling techniques to identify data integrity and security issues. For instance, a large company with numerous suppliers may discover a large payment was sent to a new financial institution, leading to a fraud investigation. The company should develop a security awareness program to help employees recognize fraudulent transfers.
- Sampling: Sampling is a statistical technique used to validate data quality by examining a sample of data. For instance, in an automotive manufacturer, assessing the quality of fasteners is not cost-effective due to the high production volume. Instead, a sample from each shipment is evaluated against the specifications for that fastener. This approach is best done in partnership with a statistician. In a streaming media company, assessing the quality of each movie transmitted across a network connection is cost-effective.
- Cross-Validation: Cross-validation is a statistical technique used by analysts to evaluate the performance of predictive models. It divides data into two subsets: the training set and the testing set. The model is built using the training data and cross-validated to determine its accuracy. Cross-validation helps identify data sampling issues, such as sampling bias, which can lead to inaccurate predictions.

NOTES - High-quality data is crucial for analytical purposes, and a good analyst must understand its importance, cleaning techniques, and verification methods. Data duplication and redundancy are common issues in complex systems, and outliers can significantly impact statistical analysis. Analyzing data requires understanding data sources and manipulation techniques, such as merging or blending sources or concatenating columns. Normalizing data values helps avoid exaggerating the impact of columns based on numeric values. Recognizing potential data quality errors and implementing quality improvements in data collection and preparation processes is essential. Assessing data quality involves defining business objectives through data accuracy, completeness, consistency, uniqueness, and validity. Continuously assessing data quality involves various methods, including reasonable expectations, audits, and advanced statistical techniques.


# Fundamentals of Statistics
- Statistics are essential for modern data analysts, as they provide a foundation for understanding different branches of the field.
- A population represents all data subjects to be analyzed, while a sample is a cost-effective and time-effective alternative.
- Variables are unique attributes of a data subject, while observations are individual records in a dataset.
- Sample size is crucial when working with statistics, as it is usually used to analyze data for a representative sample.
- For example, if you want to determine the average height for females in the United States, you would gather data from 1,000 females. The sample size represents the number of observations you select from the population.
- Analyzing samples in terms of statistics is essential, as they are numeric representations of a property of a sample and can be used to infer estimates about the population as a whole.
- Parameters, on the other hand, summarize the entire population and are dependent on the sample taken from the population.

_Common Symbols in Statstics:_
- Statistics involves numerical analysis and calculations, while emojis are used to represent emotions in texting, and statisticians use symbols to convey meaning.

# Descriptive Statstics
- Descriptive statistics summarize and describe data, aiding in understanding the size and shape of a dataset.
- It aids in univariate analysis and summary information about observations, providing context for further analysis and guiding the use of analytical techniques.

_Measures of Frequency:_
- Frequency measures help understand the frequency of events in a dataset.
- To determine the size of a dataset, count the number of observations, such as an individual's unique identifier, date, sex, and weight.
- This helps determine the tools needed to analyze the data, as 2 million observations can be analyzed on a laptop, while 2 billion observations require more computing power.

_Measures of Central Tendency:_
- An analyst uses measures of central tendency to identify the most typical value in a dataset, which are used in conjunction with other methods to understand the data's shape.
- Mean: The mean is a central tendency measurement that calculates the arithmetic average for a set of numeric values. It's commonly used in data analysis tools like spreadsheets and programming languages, but only for quantitative data.
- Median: The median is a measure of central tendency, identifying the midpoint value for all observations of a variable. It is calculated numerically and depends on the number of observations, with an odd number requiring simpler selection.

_Measures of Dispersion:_
- Understanding the spread of data is crucial, and measures of dispersion are used to provide context around it, with five common measures explored.
- Range: The range of a variable is the difference between its maximum and minimum values, which helps contextualize data, identify outliers, and identify invalid values. Spreadsheets and programming languages have functions to identify minimum and maximum values. For example, negative minimum values indicate invalid values, while positive and negative values require additional context like location and time of year.
- Distribution: Probability distributions in statistics provide probabilities and frequency of variable values, with histograms providing valuable data visualization and analysis insights. Distribution shapes include normal, skewed, and bimodal.
- Normal Distribution: The normal distribution, also known as a "bell curve," is symmetrically dispersed around its mean, giving it a distinctive bell-like shape. It is applicable across various disciplines due to the central limit theorem (CLT), a foundational theorem for statistical analysis. The CLT suggests that as sample size increases, the sampling distribution of all means will be normally distributed. The normal distribution applies to a wide variety of attributes, such as height, weight, and shoe size. To verify the normal distribution, examine the proximity of the mean and median.
- Skewed Distribution: Skewed distributions have an asymmetrical shape with a single peak and long tail, with either a right or left skew, resulting in a mean greater than the median.
- Bimodal Distribution: A bimodal distribution has two distinct modes, while a multimodal distribution has multiple modes. Visualizing a bimodal distribution shows two distinct peaks, like analyzing restaurant customer numbers over time.
- Variance: Variance is a measure of dispersion in a dataset, calculating the distance from the mean value of each observation in squared units.
- Standard Deviation: Standard deviation is a statistical measure of dispersion, indicating the average deviation between individual values and the mean.

_Each Sample is Unique:_
- Each sample from a population is unique, and if two different samples are taken, their variance and standard deviation will differ.
- 
