### **Project Description: IRCTC Mock Data Pipeline with Google Pub/Sub and BigQuery**

This project simulates a real-time data pipeline for **IRCTC (Indian Railway Catering and Tourism Corporation) user transactions** using **Google Cloud Pub/Sub** for messaging and **BigQuery** for storage and analytics. The pipeline generates synthetic user data, processes it using transformations, and stores it for further analysis.

---

### **Components & Workflow**
#### 1. **Mock Data Generation & Pub/Sub Ingestion (`irctc_mock_data_to_pubsub.py`)**
- **Generates synthetic IRCTC user data** with fields like `name`, `email`, `age`, `loyalty points`, `account balance`, etc.
- Sends generated records to a **Google Cloud Pub/Sub topic** (`irctc-data`) for real-time processing.

#### 2. **Data Transformation (`transform_udf.py`)**
- Cleans and standardizes data (capitalizes names, ensures valid emails, normalizes timestamps).
- Enriches records by **categorizing users into loyalty tiers** (`Platinum` or `Standard`).
- Computes **account age** in days from the `join_date`.
- Handles missing or invalid values with defaults.

#### 3. **BigQuery Table Creation (`bigquery_create_table.sql`)**
- Defines schema and table structure in **Google BigQuery** for storing the processed data.
- Supports structured **SQL-based analytics** on user activity, loyalty trends, and transaction patterns.

---

### **Technologies Used**
- **Google Cloud Pub/Sub** (real-time messaging & event streaming)
- **BigQuery** (data warehousing & SQL-based analytics)
- **Python** (data generation & transformation)
- **JSON** (structured data format for storage & processing)

---

