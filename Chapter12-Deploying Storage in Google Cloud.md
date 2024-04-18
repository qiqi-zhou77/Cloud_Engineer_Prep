# Deploying and Managing Cloud SQL
***MySQL instance refers to a running installation of the MySQL database server, which is a popular open-source relational database management system (RDBMS). An instance consists of the MySQL server process along with its associated system and user databases.***

Here's an explanation using an analogy:

Imagine you have a library (your computer/server) where you store books (data). Now, MySQL is like a librarian (the server software) that manages these books for you.

The MySQL instance is like the librarian's desk. It's where all the librarian's work happens - organizing books, checking them in and out, answering questions about them, etc.

Each book in the library represents a database within the MySQL instance. These databases contain tables, which are like sections or categories within the library (e.g., fiction, non-fiction, reference).

Inside each table, you have rows and columns, which are like individual books and their attributes (title, author, publication date).

So, a MySQL instance is essentially the running environment where your MySQL server operates, managing databases, tables, and their contents.

Here's an example:

Let's say you have a website where users can register and login. You would use MySQL to store user information such as usernames, passwords, and other relevant data.

Your MySQL instance would include a database called 'users'.
Inside the 'users' database, you might have tables like 'user_info', 'user_credentials', etc.
The 'user_info' table might have columns like 'user_id', 'username', 'email', 'birthdate', etc.
Each row in the 'user_info' table represents a specific user with their respective information.
So, in this example, the MySQL instance is the environment where all this user data is stored and managed by the MySQL server.


## Creating and Connecting to a MySQL Instance
## Creating a DataBase, Loading Data, and Querying Data
## Backing up mysql in Cloud SQL


# Deploying and Managing Firestore
## Adding Data to a Firestore Database
## Backing up Firestore
- create a cloud storage bucket to hold a backup file and grant appropriate permission to users performing backup





# Deploying and Managing BigQuery
## Estimating the Cost of Queries in BigQuery

## Viewing Jobs in BigQuery
- Jobs in BigQuery are processes used to load, export, copy and query data. Jobs are automatically created when you start any of these operations


# Deploying and Managing Cloud Spanner
- Create Database, Define a Schema, Insert some data, Query it
- When creating a databse, you will need to use SQL data definition language (DDL) to define the structure of tables
- Pub/Sub received the messages and keeps them until they are read by an application. Applications read msg by using subscription
- Subscription can be pulled, in which applicaiton reads from a topic; pushed, in which the subscription writes msg to an endpoint


# Deploying and Managing Cloud Pub/Sub
- creating a topic and creating a subscription
- a topic is a structure where applications can send messages


# Deploying and Managing Cloud Bigtable
- use cbt command to create tables, insert data and query tables

# Deploying and Managing Cloud Dataproc
- Google managed apache spark and hadoop service, both designed for big data applications
-  Spark supports analysis and machine learing, Hadoop is to batch, big data application
- Workflow template - define and execute workflows specified as a  directed graph of jobs
- Support serverless Spark option

# Managing Cloud Storage

