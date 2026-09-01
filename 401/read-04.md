# Read 04 - Data Modeling

## SQL vs NoSQL

### Big Picture

A database stores and organizes information so an application can
save it, retrieve it, and work with it later.

Two major approaches are SQL and NoSQL databases.

- SQL databases are relational databases.
- SQL commonly organizes data into tables with rows and columns.
- SQL databases use a predefined schema.
- NoSQL databases are non-relational or distributed databases.
- NoSQL can organize information as documents, key-value pairs,
  graphs, or wide-column stores.
- NoSQL databases can have a more flexible or dynamic schema.

### Mental Model

Think of SQL like a collection of organized spreadsheets.

Each table has a defined structure, and relationships can connect
one table to another.

NoSQL can be thought of more like storing complete information
together in flexible documents.

For example, a JSON-like document might look like:

{
  "name": "Luis",
  "books": ["The Hobbit", "The Alchemist"]
}

The structure does not have to behave exactly like rows and columns
in a relational SQL table.

---

### Complex Queries

**Question: What type of database is the best fit for a complex,
query-intensive environment?**

SQL databases are generally the better fit for a complex,
query-intensive environment.

SQL provides a powerful standardized query language for retrieving
and manipulating relational data. The assigned article notes that
NoSQL systems do not have the same standard interface for performing
complex queries.

**Quick Reference:**

Complex queries -> SQL

---

### Hierarchical Data

**Question: What type of database is the best fit for hierarchical
data storage?**

NoSQL databases are generally better suited for hierarchical data.

Document-oriented NoSQL databases can store nested information in
a structure similar to JSON. This makes related hierarchical data
natural to represent within a document.

**Quick Reference:**

Hierarchical / nested data -> NoSQL

---

### Scalability

**Question: Describe the differences in scalability between a SQL
and NoSQL database as though speaking to a non-technical friend.**

Imagine a restaurant becoming increasingly busy.

With traditional SQL scaling, you might make the existing kitchen
more powerful by buying a larger stove, more powerful equipment,
and giving that one kitchen more resources.

This is called **vertical scaling**.

SQL:
one server -> make that server more powerful

With NoSQL scaling, instead of making one kitchen bigger, you can
add more kitchens and divide the work among them.

This is called **horizontal scaling**.

NoSQL:
one server -> add more servers to share the workload

### Terms to Remember

- **SQL** = Structured Query Language
- **RDBMS** = Relational Database Management System
- **Schema** = the defined structure or blueprint of stored data
- **Relational database** = data organized into related tables
- **Vertical scaling** = increase the resources of a server
- **Horizontal scaling** = add additional servers
- **Hierarchical data** = information organized in nested levels
- **Document database** = stores related information in documents,
  often using a JSON-like structure

### Examples From the Reading

SQL:
- MySQL
- Oracle
- SQLite
- PostgreSQL
- Microsoft SQL Server

NoSQL:
- MongoDB
- Redis
- Cassandra
- CouchDB
- Neo4j

### What I Want to Remember

SQL is structured around relationships and predefined schemas and
is especially useful when I need powerful relational queries.

NoSQL offers more flexible ways of structuring data and is useful
for document-style or hierarchical information.

The simplest scalability distinction to remember is:

**SQL -> traditionally scale UP**

**NoSQL -> commonly scale OUT**

---

## SQL Modeling Techniques

### Big Picture

Before building a relational database, we should think about:

1. What information needs to be stored?
2. What tables will hold that information?
3. How are those tables related?
4. How can each record be uniquely identified?

Data modeling is the process of planning this structure before
building the database.

A useful mental model is:

Data -> Tables -> Keys -> Relationships

---

### Tables and Relationships

A relational database separates information into tables.

For example, imagine an application that stores authors and books.

Authors Table:

| author_id | name |
|-----------|------|
| 1 | Octavia Butler |
| 2 | Paulo Coelho |

Books Table:

| book_id | title | author_id |
|---------|-------|-----------|
| 101 | Kindred | 1 |
| 102 | The Alchemist | 2 |
| 103 | Parable of the Sower | 1 |

Instead of repeatedly storing all of an author's information inside
every book record, the tables can be connected using keys.

---

### One-to-Many Relationship

**Question: Among data tables, what is a one-to-many relationship
and how do we relate them?**

A one-to-many relationship means that one record in one table can
be associated with many records in another table.

Using our example:

One Author -> Many Books

Octavia Butler can have multiple books:

Author 1
   |
   +-- Kindred
   |
   +-- Parable of the Sower

We relate the tables using a **primary key** in one table and a
**foreign key** in the other.

Authors:

author_id = 1  <- Primary Key

Books:

author_id = 1  <- Foreign Key

The matching values establish the relationship.

### Mental Model

Think of a primary key as someone's unique ID number.

The foreign key is another table saying:

"This record belongs to the person with that ID."

---

### Planning the Database

**Question: Prior to designing your relational database, it might
be useful to _ a _ of the database tables and their relationships.**

Before creating the database, it is useful to make a **diagram**
of the database tables and their relationships.

A database diagram lets us visualize the structure before writing
the database code.

For example:

Authors
----------------
PK author_id
   name
       |
       | one
       |
       | many
       v
Books
----------------
PK book_id
   title
FK author_id

`PK` = Primary Key

`FK` = Foreign Key

This gives us a map of how the data will connect.

---

### Primary Key vs Foreign Key

**Question: Explain the difference between a primary and foreign key.**

A **primary key** uniquely identifies a record within its own table.

Example:

Authors

author_id = 1
author_id = 2
author_id = 3

Each author has a unique `author_id`.

A **foreign key** is a field in another table that references the
primary key.

Example:

Books

book_id = 101
title = Kindred
author_id = 1

Here:

`book_id` is the primary key for the book.

`author_id` is the foreign key connecting the book to the author
whose primary key is `1`.

### Quick Reference

Primary Key:
- Identifies THIS record.
- Must uniquely identify records in its table.
- Think: "Who am I?"

Foreign Key:
- References a record in ANOTHER table.
- Creates a relationship between tables.
- Think: "Who am I connected to?"

### Relationship Pattern

Authors:

PK author_id
      |
      |
      +----------------+
                       |
Books:                 |
                       |
FK author_id <---------+

The foreign key points back to the primary key.

---

### Things I Want to Remember

A relational database is not just a collection of separate tables.

**Keys connect the tables.**

A primary key identifies a record.

A foreign key references another table's primary key.

For a one-to-many relationship:

**ONE side -> Primary Key**

**MANY side -> Foreign Key**

Before building the database, diagramming the tables and
relationships can help reveal how the data should be organized.

---

## SQL vs NoSQL Video

### SQL Syntax: Keywords vs Parameters

**Question: How do we treat keywords and parameters differently
in SQL syntax?**

SQL keywords are conventionally written in **UPPERCASE**.

Examples of SQL keywords:

SELECT
FROM
WHERE
INSERT
UPDATE
DELETE

The values, table names, and column names used with those commands
do not need to be uppercase.

Example:

SELECT name
FROM users
WHERE id = 5;

Here:

- `SELECT`, `FROM`, and `WHERE` are SQL keywords.
- `name` is a column.
- `users` is a table.
- `id` is a column.
- `5` is a value.

### Mental Model

Think of an SQL statement like giving the database instructions:

SELECT -> What do I want?
FROM   -> Where should I look?
WHERE  -> What condition must be true?

Example:

SELECT title
FROM books
WHERE author_id = 1;

In plain English:

"Give me the title from the books where the author ID is 1."

---

## Normalization

**Question: Define normalization within the context of schemas
and data.**

Normalization is the process of organizing data into tables in a
way that reduces unnecessary duplication and keeps the data
consistent.

Instead of repeatedly storing the same information, we separate
related information into tables and connect those tables using keys.

### Without Normalization

Imagine storing:

| book | author | author_email |
|------|--------|--------------|
| Kindred | Octavia Butler | author@email.com |
| Parable of the Sower | Octavia Butler | author@email.com |
| Fledgling | Octavia Butler | author@email.com |

The author's information is repeated for every book.

If the author's email changes, we might have to update several
records.

That creates opportunities for inconsistent data.

### With Normalization

Authors:

| author_id | name | email |
|-----------|------|-------|
| 1 | Octavia Butler | author@email.com |

Books:

| book_id | title | author_id |
|---------|-------|-----------|
| 101 | Kindred | 1 |
| 102 | Parable of the Sower | 1 |
| 103 | Fledgling | 1 |

Now the author's information is stored once.

The books reference the author using:

author_id = 1

### Why Normalize?

Normalization helps:

- Reduce duplicate data.
- Improve consistency.
- Make updates safer.
- Organize related information.
- Establish clear relationships between tables.

### Mental Model

Normalization means:

**Store a fact in the appropriate place instead of unnecessarily
repeating that fact everywhere.**

---

## Database Relationships

**Question: Explain the difference between one-to-one,
one-to-many, and many-to-many relationships to a
non-technical recruiter.**

Database relationships describe how records are connected.

### One-to-One

One record is associated with one other record.

Example:

Person -> Passport

One person has one particular passport, and that passport belongs
to that person.

Think:

1 -> 1

---

### One-to-Many

One record can be associated with many other records.

Example:

Author -> Books

One author can write many books.

Think:

1 -> MANY

Authors
   |
   +---- Book
   |
   +---- Book
   |
   +---- Book

This is the relationship we used earlier with primary and
foreign keys.

---

### Many-to-Many

Many records on one side can be associated with many records on
the other side.

Example:

Students <-> Classes

One student can take many classes.

One class can contain many students.

Think:

MANY <-> MANY

A relational database commonly handles this using another table,
often called a **junction table**.

Example:

Students

student_id
name

Classes

class_id
class_name

Enrollments

student_id
class_id

The `Enrollments` table connects students with classes.

### Visual Reference

ONE-TO-ONE

Person -------- Passport


ONE-TO-MANY

Author -------- Book
       -------- Book
       -------- Book


MANY-TO-MANY

Student -------- Class
   |               |
   |               |
   +---- Enrollment ----+

---

### Quick Reference

**One-to-One**
One thing belongs to one other thing.

**One-to-Many**
One thing can have many related things.

**Many-to-Many**
Many things on either side can relate to many things on the
other side.

---

### Things I Want to Remember

SQL keywords are conventionally uppercase because it makes the
commands easier to recognize when reading a query.

Normalization organizes data so that information does not need
to be unnecessarily repeated.

Database relationships answer the question:

**"How does this piece of data connect to another piece of data?"**

Remember:

1 : 1 -> One-to-One

1 : M -> One-to-Many

M : M -> Many-to-Many

For many-to-many relationships, think:

**Junction table connects the two sides.**

---

## Sequelize API - Bookmark and Review

### What is Sequelize?

Sequelize is a Node.js ORM for working with SQL databases.

ORM stands for:

**Object-Relational Mapping**

An ORM provides a way for our JavaScript application to interact
with a relational database using JavaScript objects and methods.

### Mental Model

Without an ORM, we might communicate with a SQL database by writing
SQL directly:

SELECT * FROM users;

With an ORM such as Sequelize, our application can perform database
operations through JavaScript models and methods.

Think:

JavaScript Application
        |
        v
    Sequelize
        |
        v
   SQL Database

Sequelize acts as a layer between our JavaScript application and
the relational database.

---

### Models

A Sequelize **model** represents data that will be stored in a
database table.

For example, if our application stores books, we might have a
Book model with properties such as:

- title
- author
- description
- status

Mental model:

Model -> Table

Model instance -> Row / Record

Model attribute -> Column

For example:

Book Model
----------------
title
author
status

could correspond conceptually to:

Books Table
----------------
id | title | author | status

---

### CRUD Connection

The database operations we already know can be remembered as CRUD:

**C - Create**
Add new data.

**R - Read**
Retrieve existing data.

**U - Update**
Change existing data.

**D - Delete**
Remove data.

These ideas exist whether we are using raw SQL or an ORM.

Conceptually:

POST   -> Create
GET    -> Read
PUT    -> Update
DELETE -> Delete

This creates an important connection:

HTTP Request
     |
     v
Express Route
     |
     v
Sequelize Model
     |
     v
SQL Database

The route receives the request.

The model works with the data.

The database stores the data.

---

### Relationships in Sequelize

The relationships studied earlier can also be represented through
models.

The important concepts remain:

One-to-One

1 : 1

One-to-Many

1 : M

Many-to-Many

M : M

Sequelize provides associations for describing relationships
between models.

The important idea for now is:

**The ORM does not remove database relationships.**

It gives our JavaScript application a way to describe and work
with those relationships.

---

## Read 04 - Study Recap

### The Big Picture

A database is responsible for storing and organizing application
data.

SQL databases organize related information using tables,
schemas, keys, and relationships.

NoSQL databases provide other ways of organizing information,
including flexible document-style structures.

When designing relational data:

1. Decide what information needs to be stored.
2. Separate that information into logical tables.
3. Give records identifiers using primary keys.
4. Connect related tables using foreign keys.
5. Determine the relationships between the tables.
6. Avoid unnecessary duplication through normalization.
7. Use queries or an ORM to interact with the stored data.

---

### Read 04 Mental Map

DATA MODELING
     |
     +--> SQL
     |     |
     |     +--> Tables
     |     +--> Schema
     |     +--> Primary Keys
     |     +--> Foreign Keys
     |     +--> Relationships
     |     +--> Normalization
     |
     +--> NoSQL
     |     |
     |     +--> Flexible structures
     |     +--> Documents
     |     +--> Hierarchical / nested data
     |
     +--> Sequelize
           |
           +--> JavaScript
           +--> Models
           +--> Relationships
           +--> CRUD
           +--> SQL Database

---

## Things I Want to Remember

### SQL vs NoSQL

SQL:
- Relational
- Tables
- Defined schemas
- Strong relational querying
- Traditionally associated with vertical scaling

NoSQL:
- Non-relational approaches
- Flexible structures
- Often useful for document and hierarchical data
- Commonly associated with horizontal scaling

### Keys

Primary Key:

**Identifies the record.**

Foreign Key:

**Connects the record to another table.**

### Relationships

1 : 1 = One-to-One

1 : M = One-to-Many

M : M = Many-to-Many

### Normalization

Organize information so the same facts do not need to be
unnecessarily repeated.

### Sequelize

Sequelize is an ORM that allows a Node.js application to work
with relational database data through JavaScript models and
methods.

### One Sentence to Remember

**A data model describes what our data looks like, how it is
organized, and how the different pieces of data relate to
each other.**

