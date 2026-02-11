# Data Modeling

This project extracts data from .csv files, puts it into a Postgre database, and at the end makes an exploratory data analysis.

## Description

The data content is about the World Wealth of each country broken down into several topics.

The data model is the following below:

![alt text](https://github.com/ugrodrigo/data_modeling_project/blob/main/Data%20Model.jpg)

## Getting Started

### Dependencies

* Python 3.11.3
* Pandas 2.0.2
* psycopg2 2.9.6
* matplotlib 3.7.1
* Postgre 15.3-3

### Installing

First, install Postgre on your computer [link](https://www.postgresql.org/download/)

After defining your default dbname, user, and password you must insert it on the second cell of the code:
``` 
def create_database():
    # connection to the default database
    conn = psycopg2.connect("host=127.0.0.1 dbname=postgres user=postgres password=root")
    conn.set_session(autocommit=True)
    cur = conn.cursor()

    # Creating a new database named accounts
    cur.execute("DROP DATABASE IF EXISTS accounts")
    cur.execute("CREATE DATABASE accounts")

    # Close connection to the default database
    conn.close()

    # connection to the new database
    conn = psycopg2.connect("host=127.0.0.1 dbname=accounts user=postgres password=root")
    cur = conn.cursor()

    return cur, conn
```
You must change the function **psycopg2.connect()** to your configuration.

## License

This project is licensed under the MIT License - see the LICENSE file for details
