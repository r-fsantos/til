# Database Management System — BDMS

This notes say respect to my learnings on DBMSs from and to the point of view of designers, users and developers.

DBMS provides efficient, reliable, convenient, and very safe multi-user data storage. Allows access and manipulation of huge amounts of persistent data.

Talking a little bit more about the key points mentioned above.

- **Massive**: We live in a era of big data at scale of terabytes.
- **Persistent**: Data not always live on the program memory. It needs to be stored carefully for late reads, updates and deletion.
- **Safe**: Safe, by definition, is a major concern.  DBMS are designed to be reliable, safe, and imune to software issues. Hardware issues can occur, obviusly.
- **Multi-user:** It is reasonable to supose that it is note performatic to allow dabatase access one user a time. In order to allow multi-user, concurrency and paralelism are know at this domain as Concurrency-Control. Data are unique, so there are many ways of one user to access the same data, for instance.
- **Convenient:** That is a bit and important point. I'll break it into smaller ones for the sake of learning and readability.
    - DBMS are hardware independent. Or one can say Physical Data Independent. DBMS imposes some layers of Abstraction on top of Physical Devices, like hard-drives, SSDs, etc.
    - Data are accessed by means of a specific language. Known as Data Query Languages. Such languagues are, obviusly agnostic from OSs. DBMSs are inherently designed to work with large amounts of data, proccess on top of it.
    - Data Query Languages at DBMS are declaritive. That means that one just describes what he wants, how he want and from where he wants. The DBMSs takes care of the rest. That is very huge deal: The way on how data is searched, ordered, filtered, grouped and other processing types are ENTIRELY DONE BY DBMS. That is really fantastic.

It is convenient to say that data structures at application level and way more different from the data structures of DBMS. 

# Where they are used?

Ok, they are awesome, if you read the previous heading and pay attention.

You are probably using one right now. I'm probably using one to store all this notes at Notion.

## Seriouly, DBMS can...

- Be consumed and programmed by other layers of abstraction provided by frameworkes. Typical examples are Django, Ruby on Rails
- Be executed in conjunction with middlewares. Some examples: Application servers, web-servers.
- Data-intensive applications may not use DBMS at all. Hadoop is an example of that situation. It is an system that can read lots and lots of files.

# Key Concepts

- **Data Model:** How data is structured. Can be in a relational way, on xml, on graphs (nodes, edges)
- **Schema Vs Data:** Schemas are the structure, how data can relate to each other. The primitive data types known like integers, floats, arrays of chars, booleans. And also their precision, lenght. Data are data. Are the information that needs to be persisted accordingly with DBMS schema.
- **Data Definition Language — DDL:** High level design language, responsible for setting up the schema.
- **Data Query Language (DQL) or Data Manipulation Language (DML):** Declarative language responsible for querying and modifying the data. ****