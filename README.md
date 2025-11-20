Black Friday Sales Analysis

📌 Project Overview

This project provides an end-to-end data analysis solution for the Black Friday Sales dataset. It involves an ETL (Extract, Transform, Load) pipeline using Python to clean and migrate raw CSV data into a MySQL database, followed by a comprehensive business intelligence dashboard in Power BI to track revenue, customer demographics, and product performance.

📂 Dataset

The dataset contains ~550,000 observations of customer purchases.

Source: Black Friday Dataset (or derived source).

Features: User demographics (Age, Gender, Occupation, Marital Status), City Category, Product Categories, and Purchase Amount.

🛠️ Tech Stack

ETL & Scripting: Python (Pandas, MySQL Connector)

Database: MySQL

Visualization: Power BI

Version Control: Git

🚀 Setup Instructions

1. Database Configuration (MySQL)

Log in to your MySQL instance.

Create the database and table using the schema provided below:

CREATE DATABASE black_friday_db;
USE black_friday_db;

CREATE TABLE black_friday_sales (
    User_ID INT,
    Product_ID VARCHAR(20),
    Gender CHAR(1),
    Age VARCHAR(10),
    Occupation INT,
    City_Category CHAR(1),
    Stay_In_Current_City_Years VARCHAR(5),
    Marital_Status TINYINT,
    Product_Category_1 INT,
    Product_Category_2 INT DEFAULT NULL,
    Product_Category_3 INT DEFAULT NULL,
    Purchase INT
);


2. Python Environment Setup

Clone this repository.

Install the required dependencies:

pip install pandas mysql-connector-python numpy


Secure your credentials:
Create a file named config.py in the root directory (this file is ignored by Git for security):

# config.py
db_config = {
    'user': 'root',
    'password': 'YOUR_PASSWORD',
    'host': 'localhost',
    'database': 'black_friday_db'
}


3. Running the ETL Pipeline

Run the insertion script to clean the data and load it into MySQL:

python insert_black_friday.py


Note: The script processes data in chunks of 1000 rows to ensure memory efficiency.

📊 Power BI Dashboard Layout

The dashboard is designed with three main pages:

Page 1: Executive Summary

High-level KPIs for management.

Key Metrics: Total Revenue, Total Transactions, Average Order Value (AOV).

Visuals: Sales by Gender (Donut), Sales by City Tier (Bar), Top Occupations.

Page 2: Customer Demographics

Deep dive into buyer personas.

Visuals: Purchase behavior by Age Group, Marital Status impact, and spending habits based on Length of Stay in the city.

Page 3: Product Performance

Inventory and merchandising insights.

Visuals: Volume vs. Value Scatter Plot, Decomposition Tree for Category Analysis (Drill-down).

🛡️ Security Note

This repository includes a .gitignore file to prevent sensitive configuration files (like config.py) and large data files from being committed to version control.

📝 License

This project is open-source and available under the MIT License.
