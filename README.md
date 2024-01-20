# Data Cleaning Pipeline

## Description

This project is a DAG that will run data cleaning and analysis on a dataset of your choice.

# Data Cleaning Pipeline

## Description

This project is a DAG that will run data cleaning and analysis on a dataset of your choice.

## Installation and Use of the DAG

Follow these instructions to set up and use the Apache Airflow DAG in your local environment.

### Prerequisites

Before you start, you will need Apache Airflow installed on your system. See the Apache Airflow Installation section for
detailed instructions.

### DAG Configuration

1. **Clone the Repository**:
    - Clone the repository that contains the DAG to your local environment:
      ```bash
      git clone https://github.com/santannaflaercio/data-cleaning-pipeline.git
      ```

2. **Copy the DAG to the Airflow DAGs Folder**:
    - Copy the `.py` file of the DAG to the Airflow DAGs folder:
      ```bash
      cd data-cleaning-pipeline
      cp data_cleaning.py ~/airflow/dags/
      ```

### Using the DAG

1. **Start the Airflow Web Server**:
    - Start the Airflow web server to access the user interface (UI) and the Airflow Scheduler to sync the DAG with the
      Airflow database:
      ```bash
      airflow standalone
      ```

2. **Activate the DAG**:
    - Access the Airflow UI at `localhost:8080`, navigate to the list of DAGs, find your DAG and click on the toggle
      button to activate it.

3. **Monitor the DAG Execution**:
    - Use the Airflow UI to monitor the execution of the DAG and check logs and results.

### Examples

The following table presents a sample dataset that includes information about various individuals. Each row represents a
unique record and each column represents a specific data field. The data is saved in the `raw_data_sample.csv` file,
located in the `reference_files` folder. The file contains the following fields:

- `id`: This is the unique identifier for each record.
- `name`: This is the individual's name.
- `age`: This is the individual's age. Note that some records may not have this information.
- `salary`: This is the individual's salary. Note that some records may not have this information.

Here is the table:

| id | name           | age | salary |
|----|----------------|-----|--------|
| 1  | John Doe       | 30  | 50000  |
| 2  | Jane Smith     | 25  | 60000  |
| 3  | Bob Johnson    |     | 70000  |
| 4  | Alice Williams | 28  |        |
| 5  | Chris Davis    | 22  | 40000  |
| 6  | Emma Watson    | 30  | 50000  |
| 3  | Bob Johnson    |     | 70000  |
| 7  |                | 35  | 80000  |
| 8  | John Doe       | 30  | 50000  |

The following table presents the same dataset after it has been cleaned. The data is saved in
the `clean_data_sample.csv` file, located in the `reference_files` folder. The file contains the following fields:

| id | name        | age  | salary  |
|----|-------------|------|---------|
| 1  | John Doe    | 30.0 | 50000.0 |
| 2  | Jane Smith  | 25.0 | 60000.0 |
| 5  | Chris Davis | 22.0 | 40000.0 |
| 6  | Emma Watson | 30.0 | 50000.0 |

The following table presents the same dataset after it has been analyzed. The data is saved in the `analysis_sample.csv`
file, located in the `reference_files` folder. The file contains the following fields:

|     | id  | age  | salary  |
|-----|-----|------|---------|
|count| 4.0 | 4.0  | 4.0     |
|mean | 3.5 | 26.75| 50000.0 |
|std  | 2.38| 3.95 | 8164.97 |
|min  | 1.0 | 22.0 | 40000.0 |
|25%  | 1.75| 24.25| 47500.0 |
|50%  | 3.5 | 27.5 | 50000.0 |
|75%  | 5.25| 30.0 | 52500.0 |
|max  | 6.0 | 30.0 | 60000.0 |