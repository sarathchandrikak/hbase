# HBase

  # 📍 HBase basic concepts 
     
## 👉 Introduction
 1. Hbase is a non relational distributed platform that stores data in Columnar basis (Based on Column names)
 2. It is built on HDFS & can leverage all the features that are offered by the HDFS
 3. It is released as an open-source implementation of Google's Bigtable.

## 👉 Features of HBase
1. Distributed storage: HBase is a distributed, column-oriented database 
2. Flexible schema: HBase does not follow any strict schema, i.e., you can add any number of columns dynamically to an HBase table. HBase columns do not have any specific data type, and all the data in HBase is stored in the form of bytes.
3. Sorted: HBase records are sorted by RowKey. Every HBase RowKey must be unique, i.e., no two rows can have the same RowKey. 
4. Data replication: HBase supports the replication of data across a cluster.
5. Faster lookups: HBase stores data in indexed HDFS files and uses HashMap internally. It also allows random access to the data. This enables faster lookup.
6. Horizontal scalability: HBase is horizontally scalable. This means if the clusters require more resources, HBase can scale up according to the need. HBase can horizontally scale up to thousands of commodity servers.

## 👉 Components of HBase 
1. Tables: HBase tables are collections of rows and columns. Basic CRUD operations Create, Read, Update and Delete, can be performed on tables using HBase shell commands or the API. 
2. Rows: Rows are a collection of column families. Rows are sorted on the basis of the RowKey of a table. A RowKey is used to uniquely identify a record. The design of the row key optimises the scan, as related rows are stored together, or rows that are read together are stored together.
3. Column families: These are collections of columns. The column qualifiers integrated with the column family name are used to identify a single column. Each row in an HBase table can have multiple column families, and one or more columns can be associated with each column family. 
4. Version: The data in an HBase table is stored in a cell. A cell is a combination of a RowKey, a column family and a column qualifier. It contains a value and a timestamp. The data stored in a cell can have multiple versions. Each version is identified using its own timestamp.


To access data from HBase table, 4 parameters are needed. RowKey, Column Family, Column Name, version. This is the reason HBase is also known as 4 Dimension data model. 

  # 📍 HBase Data Model 
  
<img src="https://github.com/sarathchandrikak/hbase/blob/main/hbase.jpeg"
     alt="Markdown Monster icon"
     style="float" /> 
     
Image Source: https://www.oreilly.com/library/view/hadoop-essentials/9781784396688/ch05s04.html


  # 📍 HBase basic queries 
    
Start HBase shell

        hbase shell 
        
Creating table in HBase

        create '<table_name>', 'column_family' 
        
Alter table in HBase

        alter '<tablename>', 'add/modify/delete'=> '<column familyname>'
        
Insert data into HBase 

        put '<table_name>', '<row_key>', '<column_value>', '<value>'
        
Fetch data from HBase
        
        get '<table_name>', '<row_key>', {'TIMERANGE'/'TIMESTAMP'/'VERSIONS' and 'FILTERS'}

View entire data table 
        
        scan '<table_name>' {Optional parameters} 
        
        Optional Parameters: TIMERANGE, FILTER, TIMESTAMP, LIMIT, MAXLENGTH, COLUMNS, CACHE, STARTROW and STOPROW.
        
Drop data table

        drop '<table name>'

Truncate to delete all the data from the existing data table

        truncate '<table_name>'
 
 Check whether table is enabled
 
        is_enabled '<table_name>'
  
  Disable data table
        
        disable '<table_name>'
