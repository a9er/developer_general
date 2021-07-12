# Relational Databases

Applications commonly process data - and that data needs to be processed somewhere. A [relational database](https://en.wikipedia.org/wiki/Relational_database) is one of the most common ways that data is stored; using the [relational model](https://en.wikipedia.org/wiki/Relational_model), data is organized into *tables* which contain *columns* and *rows* - similar to how things would be stored in a spreadsheet.

## SQL

[Structured Query Language](http://www.sqlcourse.com/intro.html) or *SQL* is one of the most common ways of interacting with a relational database. While standards exist (say, *ANSI-SQL*), most SQL code is not completely portable across several relational database management systems.

[DDLs and DMLs](https://www.w3schools.in/mysql/ddl-dml-dcl/) are different groups of SQL commands. DDL stands for *Data Definition Language* which declares how data should *reside* in a database. DML stands for *Data Manipulation Language* which deals with storing, updating, or deleting data inside a database.

## Relational Database Management Systems

Many relational database management systems exist on the market - a lot of which are free. They all come with their own quirks and features - which you'll come to know over your journey.

[MySQL](https://dev.mysql.com/doc/refman/5.7/en/tutorial.html) is the most popular open source RDBMS in the world. Install it, get to know it - you'll bump into it quite often.

[PostgreSQL](http://www.postgresqltutorial.com/) declares itself the most advanced open source RDBMS - and for the most part, that claim is true. It also boasts complete ACID and SQL compliance.

## Checkpoint 1: Create databases

Install both MySQL and PostgreSQL on your laptop, and try to create tables on them using the tutorials. Note the differences in access requirements and query structure.

## More Abstract terms

[ACID](https://en.wikipedia.org/wiki/ACID) is a set of properties of database transactions intended to guarantee validity even in the event of errors. Understand why this is important - especially when hundreds of thousands of people are updating their data in real time.

[CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem) applies to distributed data stores - which is important when it comes to databases, as you don't want all your eggs (or data) to be in a single point of failure. While outdated, the basic principles apply.

[PACELC Theorem](https://en.wikipedia.org/wiki/PACELC_theorem) is an extension to CAP Theorem which accounts for operation when no network partitioning or errors occur. This also encompasses NoSQL or BASE databases.

[Database Normalization](http://www.studytonight.com/dbms/database-normalization.php) are techniques on how to organize database columns to reduce redundancy and improve data integrity. Understand *why* we organize our databases in different ways.

## Checkpoint 2: Explain databases

Explain when you would use MySQL over PostgreSQL - and when ACID compliance would matter the most.
