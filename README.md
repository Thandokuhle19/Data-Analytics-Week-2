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
- 

