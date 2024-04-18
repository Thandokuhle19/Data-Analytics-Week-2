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
- 
