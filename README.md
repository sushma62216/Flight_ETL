# Flight ETL & Live Flight Activity Dashboard

## About the Project
This project demonstrates an end-to-end data pipeline that extracts real-time flight data from the OpenSky Network API, performs cleaning and transformation using Python, and loads the data into a PostgreSQL database. The processed data is then visualized through an interactive Streamlit dashboard, enabling live insights into global flight activity. The project highlights both data engineering and data analysis.

---

## Skills Demonstrated
- Python scripting for API data extraction and data transformation with Pandas  
- PostgreSQL database design, table creation, and SQL query optimization  
- Building interactive dashboards using Streamlit for data visualization  
- Secure configuration management using environment variables

---

## Main Files Explained

| File           | Description                                                                                 |
|----------------|---------------------------------------------------------------------------------------------|
| `extract.py`   | Contains functions to call the OpenSky API and retrieve raw flight data in JSON format.     |
| `transform.py` | Cleans and transforms the raw data into structured Pandas DataFrames suitable for loading.  |
| `load.py`      | Handles creating tables and loading transformed data into PostgreSQL tables.                |
| `retrieve_data.py` | Contains reusable functions to query PostgreSQL and return data as Pandas DataFrames.   |
| `db_schema.py` | Defines the PostgreSQL database schema, including SQL commands to create tables and indexes. |
| `db_config.py` | Loads database connection credentials securely from environment variables using dotenv.     |
| `app.py`       | Streamlit application that loads data from the database and visualizes flight activity.     |

---

## Getting Started

### Prerequisites

- Python 3.8 or above  
- PostgreSQL database server  
- Required Python packages (`psycopg2-binary`, `pandas`, `streamlit`, `python-dotenv`)

### Installation & Setup

1. Clone this repository  
2. Create and activate a virtual environment  
3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Create a `.env` file in the project root folder with your PostgreSQL credentials in this format:

    ```
    DB_HOST=localhost
    DB_NAME=opensky
    DB_USER=your_username
    DB_PASSWORD=your_password
    DB_PORT=port_number
    ```

5. Ensure your PostgreSQL database is running and the database name matches the `.env` config.

6. Run the ETL pipeline to populate your database:

    ```bash
    python main.py
    ```

7. Start the Streamlit dashboard:

    ```bash
    streamlit run app.py
    ```

8. Open your browser at `http://localhost:8501` to interact with the dashboard.

---

## Enhancements to be made in future ETL projects

- Automate pipeline runs using Apache Airflow or OS schedulers
- Implement error handling, logging, and monitoring for ETL processes
- Use dbt for managing data transformations, testing, and documentation to improve data modeling and pipeline maintainability.
- Add unit and integration tests for the ETL functions  
- Containerize the app with Docker for easy deployment  

---

