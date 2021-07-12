# NoSQL

In contrast with relational databases, NoSQL databases provide mechanisms for the storage and retrieval of data that foregoes the table-based relations used in relational databases. It's arguably a *"simpler"* approach to storing data, as well as providing for easier horizontal scaling and availability control.

## Basic concepts

[There are several types of NoSQL databases](https://en.wikipedia.org/wiki/NoSQL#Types_and_examples_of_NoSQL_databases), each with their own specific use case and things they are good at.

[Document stores](https://en.wikipedia.org/wiki/Document-oriented_database) are designed for storing, retrieving, and managing [semi-structured data](https://en.wikipedia.org/wiki/Semi-structured_data) - typically in JSON or XML. Document stores store all information for a given object in a single instance in the database, and every stored object can be different from every other. Contrast this with relational database, where every row has to follow a table's schema.

[CouchDB](https://couchdb.apache.org/) is a document store that focuses on availability. Install it, and try to store a little bit of data [with their neat little tutorial](http://guide.couchdb.org/draft/tour.html).

[Redis](https://redis.io/) is slightly different from CouchDB in that it is a *data structures server*. It supports multiple data structures like [strings](https://en.wikipedia.org/wiki/String_(computer_science)), [hashes](https://en.wikipedia.org/wiki/Hash_table), [lists](https://en.wikipedia.org/wiki/List_(abstract_data_type)), [bitmaps](https://en.wikipedia.org/wiki/Bitmap) etcetera, etcetera. Try their [nifty little tutorial](https://try.redis.io/).

## Checkpoints

Install the same data set that you did with relational databases. Look at the differences. Note: you don't have to have the same number of objects in your "row", right?

## Advanced concepts

[BASE](https://en.wikipedia.org/wiki/Eventual_consistency) stands for Basically Available, Soft State, and Eventual Consistency. Contrast with the ACID model.