# [Data Warehouse](https://learn.microsoft.com/en-us/training/modules/get-started-data-warehouse/2-understand-data-warehouse)

## Data Warehouse Introduction
The process of building a modern data warehouse typically consists of:

* Data ingestion - moving data from source systems into a data warehouse.
* Data storage - storing the data in a format that is optimized for analytics.
* Data processing - transforming the data into a format that is ready for consumption by analytical tools.
* Data analysis and delivery - analyzing the data to gain insights and delivering those insights to the business.

Microsoft Fabric enables data engineers and analysts to ingest, store, transform, and visualize data all in one tool with both a low-code and traditional experience.


## Data Warehouse Design
Like all relational databases, Fabric's data warehouse contains tables to store your data for analytics later.
Like all relational databases, Fabric's data warehouse contains tables to store your data for analytics later.

### Data Warehouse Table Design

#### Fact Table
* Contain the numerical data that you want to analyze.
* Typically have a large number of rows and are the primary source of data for analysis. 

#### Dimension Table
* Contain descriptive information about the data in the fact tables
* Typically have a small number of rows and are used to provide context for the data in the fact tables
* Include two key columns
  * Surrogate Key
    * Unique identifier for each row in the dimension table. It's often an integer value that is automatically generated by the database management system when a new row is inserted into the table.
    * Specific to the data warehouse and help to maintain consistency and accuracy in the data
  * Alternate Key
    * Natural or business key that identifies a specific instance of an entity in the transactional source system - such as a product code or a customer ID
    * specific to the source system and help to maintain traceability between the data warehouse and the source system.
   
#### Special Dim Tables
Time dimensions provide information about the time period in which an event occurred. This table enables data analysts to aggregate data over temporal intervals. 
For example, a time dimension might include columns for the year, quarter, month, and day in which a sales order was placed

### Schema Design
* In most transactional databases that are used in business applications, the data is normalized to reduce duplication. 
* In a data warehouse however, the dimension data is generally de-normalized to reduce the number of joins required to query the data

A data warehouse is organized as a star schema, in which a fact table is directly related to the dimension tables, as shown in this example

<img src= "https://github.com/user-attachments/assets/5aae9dba-c4b6-49b4-8928-ed1ac3a6dd54" width="500"></img>

Alternatively, a snowflake schema is used if there are lots of levels or some information is shared by different things

<img src= "https://github.com/user-attachments/assets/3737bc4b-ca96-48ab-84c9-908e0dc517a5" width="500"></img>

# [Loading into Data Warehouse](https://learn.microsoft.com/en-us/training/modules/load-data-into-microsoft-fabric-data-warehouse/2-explore-data-load-strategies)

## Data Ingestion vs. Data loading
* **Data ingestion/extract** is about moving raw data from various sources into a central repository
* **Data loading** involves taking the transformed or processed data and loading it into the final storage destination for analysis and reporting

## Type of Data Loading

<img src = "https://github.com/user-attachments/assets/48161b1f-a522-4292-aeb4-365ac3dde1eb" width="500"></img>

## T-SQL vs. Dataflow Gen2


