# Polpular Databases
    > Mysql
    > MariaDB
    > Db2
    > Oracle
    > DynamoDB
    > PostgreSQL
    > Microsoft SQL server
    > Amazon Aurora
# DBA Role
    > Server
    > Security
    > Performance
    > If fail then manage
    > If hack then manage
    > How to migrate
    > Sql query

# Single Tier Website

*  Website, Database server on one system.

# Multi-Tier Architechture

* Website at one place and Database server at another place.
* Website user cannot access Database directly.

# RDS (Relational Database Services)

* One of the highest paid service of AWS.
* It is the automation collection of almost all the popular database
* It provides required hardware resources as well.

## To Connect client and server
    * mysql -u <username> -h <url> -p 

## To connect from python
    * pip3 install mysql-connector-python


```
#!/usr/bin/python                                                   
import mysql.connector as mysql                                                                                                                      


# RDS info


u='<username>'<br>
p='<password>'<br>                             
db='<database_name>'<br>
h='<url>'                                                                           
#### now connecting 
conn=mysql.connect(user=u,password=p,database=db,host=h)

#### now generating a sql language cursor                       
cur=conn.cursor()

#### now we can write sql query                                 
cur.execute("show tables;")                                                                                      
#### now printing result                                        
print(cur.fetchall())                                                                            
#### closing connection
conn.close()
```
## Database Migration
    
    * Migrate database from one server to another.
    * mysql -u <username> -h <url> -p <existing database> < <database to migrate>
