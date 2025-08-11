# 🛠️ Data Engineering Pipeline

This repository contains a modular data pipeline built using Python, Apache Airflow, DBT, and Snowflake. It supports data extraction from MySQL, PostgreSQL, and MongoDB, transformation using Python and DBT, and loading into Snowflake.

---

## 📁 Folder Structure

- `dags/`: Airflow DAGs for orchestrating tasks
- `scripts/`: Python scripts for extract, transform, and load
- `dbt_project/`: DBT models and configurations
- `config/`: Database connection settings
- `data/`: Raw and processed data files
- `tests/`: Unit tests for transformation logic
- `logs/`: Airflow and script logs
- `.env`: Environment variables
- `requirements.txt`: Python dependencies

---

## 🚀 Getting Started

### 1. Install Dependencies

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
### 2. Configure Environment
Create .env file with your database credentials or use the config files in /config

```bash

MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=yourpassword
MYSQL_DB=yourdatabase

```

### 3. Run Extract Script

```bash
py scripts/extract/from _mysql.py
```
### 4. Run Airflow DAG
```bash
airflow db init
airflow scheduler
airflow webserver
```
trigger the DAG via Airflow UI or CLI:
```bash
airflow dags trigger mysql_extract_pipeline
```
---
### 🧪Testing
```bash
pytest tests/
```
---
## 📚 Technologies Used
### Python
Used for scripting ETL processes, data cleaning, and integration with databases and APIs. Libraries like pandas, sqlalchemy, and mysql-connector-python are used for data manipulation and connectivity.
### 🛫 Apache Airflow
Serves as the orchestration tool to schedule and monitor workflows. DAGs are defined using Python and can trigger tasks like data extraction, transformation, and loading.
### 🧱 DBT (Data Build Tool)
Used for transforming data in the warehouse using SQL. DBT enables modular, testable, and version-controlled transformations with support for documentation and testing.
### 🗄️ MySQL / PostgreSQL / MongoDB
These databases serve as data sources:
- MySQL & PostgreSQL: Relational databases used for structured data.
- MongoDB: NoSQL database used for semi-structured or document-based data.
### ❄️ Snowflake
Cloud-based data warehouse used as the destination for transformed data. DBT models are executed here to create analytics-ready datasets.

---
## 👨‍💻 Author
Muhammad Thariq Trikusuma
