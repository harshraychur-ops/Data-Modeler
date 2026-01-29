Data Modeler – Building a Normalized Star Schema Data Model

Project Objective

The objective of this project is to design and implement a well-structured relational data model in Power BI using normalized tables. The project focuses on understanding data modeling concepts such as table relationships, cardinality, star and snowflake schemas, handling inactive relationships, and building hierarchies using Power Query and Model View only, without using DAX.

Data Sources

The following Excel files were used as source data:

Sales Fact.xlsx

Customer Dim.xlsx

Product Dim.xlsx

Region Dim.xlsx

Date Dim.xlsx

Returns Fact.xlsx

Each file represents either a fact table or a dimension table and was imported using Power Query.

Data Preparation (Power Query)

Imported all Excel files into Power Query

Removed blank rows and ensured first rows were promoted as headers

Renamed queries and columns for clarity and consistency

Assigned appropriate data types (whole numbers, decimals, dates, text)

Loaded cleaned tables into the Power BI data model

Data Model Design

Implemented a Star Schema with Sales_Fact as the central fact table

Connected dimension tables (Customer, Product, Region, Date) directly to Sales_Fact

Modeled Returns_Fact as a secondary fact table linked to Sales_Fact

Created relationships manually to reflect primary and foreign key logic

Relationships and Cardinality

All relationships were defined as one-to-many (1:*) from dimension tables to fact tables

Single-direction cross-filtering was applied to avoid ambiguity and improve performance

An inactive relationship was created between Returns_Fact and Date_Dim using ReturnDateKey to demonstrate handling of multiple date relationships

Hierarchies and Enhancements

Created hierarchies for better data navigation:

Date_Dim: Year → Quarter → Month → Date

Region_Dim: Country → State → City

Product_Dim: Category → Subcategory → Product Name

Set appropriate data categories for geographic and descriptive fields

Verification

A Matrix visual was used to validate the data model by checking:

Sales by Product Category and Region

Return reasons by Fiscal Year

Revenue by Customer Segment

This confirmed that relationships, filters, and hierarchies function correctly.

Issues Faced and Resolution

An ambiguous relationship scenario occurred due to multiple links between fact tables and the Date_Dim table. This was resolved by keeping the Sales_Fact to Date_Dim relationship active and setting the Returns_Fact to Date_Dim relationship as inactive, ensuring correct filter flow.
