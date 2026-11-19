# P3G7-PerfectPetClub-Customer-Churn
Customer churn analysis using Python ETL and Matplotlib dashboard.

## 1. Project Overview

The **PerfectPetClub Customer Churn Analysis** project focuses on analysing customer subscription behaviour and identifying patterns associated with customer churn.

The project uses data engineering techniques and Python-based data analysis to extract, clean, transform and combine information from multiple sources. These sources include a SQLite database, customer relationship management (CRM) records, website server logs and customer survey responses.

An Extract, Transform and Load (ETL) pipeline is developed to integrate the available data into a structured analytical dataset. The processed data is stored in Parquet format and used to create a customer churn dashboard using Python and Matplotlib.

The overall aim is to understand customer retention patterns and identify behavioural factors that may be associated with subscription cancellations.

## 2. Project Objectives

The main objectives are:

- Extract data from the provided SQLite database and CSV files.
- Clean and prepare data from multiple sources.
- Integrate customer information using appropriate identifiers.
- Create additional features to support customer churn analysis.
- Define customer churn based on automatic subscription renewal status.
- Store the transformed dataset in Parquet format.
- Analyse customer behaviour and subscription patterns.
- Develop visualisations to communicate important findings.
- Present key performance indicators through a customer churn dashboard.
- Use Git and GitHub to support version control and team collaboration.

## 3. Technologies and Tools

| Technology | Purpose |
|---|---|
| Python | Main programming language for ETL and analysis |
| Jupyter Notebook | Development and execution of Python code |
| Pandas | Data cleaning, manipulation and analysis |
| NumPy | Numerical operations |
| SQLite3 | Extracting data from the SQLite database |
| Boto3 | Accessing survey data from the provided S3-compatible storage |
| PyArrow | Reading and writing Parquet files |
| Matplotlib | Data visualisation and dashboard development |
| Git | Source code version control |
| GitHub | Repository hosting and team collaboration |

## 4. Project Structure

The project is organised into the following folders and files:

```text
P3G7-PerfectPetClub-Customer-Churn/
│
├── Data/
│   ├── PerfectPetClub.db
│   ├── PerfectPetClub_CRM_report.csv
│   ├── PerfectPetClub_server_log.csv
│   ├── PerfectPetClub_survey.csv
│   ├── PerfectPetClub_survey_questions.txt
│   └── customer_churn.parquet
│
├── notebooks/
│   ├── ETL.ipynb
│   ├── ETL.html
│   ├── Dashboard.ipynb
│   └── Dashboard.html
│
├── customer_churn_dashboard.png
├── .gitignore
└── README.md
```

**Note:** The source datasets and notebooks may be maintained locally and are not necessarily included in the GitHub repository. Check the repository contents before running the project.

## 5. Data Sources

The project uses the following datasets:

### 5.1 PerfectPetClub SQLite Database

`PerfectPetClub.db`

The SQLite database contains customer and business-related information, including customer, subscription, payment, sales, product and product review records.

### 5.2 Customer Relationship Management Data

`PerfectPetClub_CRM_report.csv`

Contains customer service interaction records used to examine customer support activity and complaint patterns.

### 5.3 Website Server Log Data

`PerfectPetClub_server_log.csv`

Contains customer website and application login activity. These records support the analysis of customer engagement.

### 5.4 Customer Survey Data

`PerfectPetClub_survey.csv`

Contains customer survey responses, including reported income, recommendation scores, satisfaction scores and online price comparison frequency.

### 5.5 Survey Questions

`PerfectPetClub_survey_questions.txt`

Provides information about the questions associated with the customer survey.

## 6. ETL Pipeline

The ETL pipeline is developed using Python and consists of three main stages: Extract, Transform and Load.

### 6.1 Extract

The extraction stage collects data from different sources.

The process includes:

- Connecting to the SQLite database.
- Extracting relevant database tables.
- Reading CRM records from CSV files.
- Loading website server log information.
- Accessing customer survey information from the provided S3-compatible storage.
- Loading the required datasets into Pandas DataFrames.

### 6.2 Transform

The transformation stage prepares the extracted information for customer churn analysis.

The process includes:

- Checking the structure and quality of the extracted datasets.
- Removing unnecessary and sensitive fields from the analytical dataset.
- Checking customer identifiers and data consistency.
- Combining customer and subscription information.
- Aggregating sales and payment information.
- Calculating CRM interaction and complaint counts.
- Aggregating customer login activity.
- Integrating customer survey information.
- Creating a churn indicator based on automatic renewal status.
- Handling missing values in engineered activity features.

These transformations help create a structured dataset containing relevant customer information for further analysis.

### 6.3 Load

The final transformed dataset is saved in Parquet format.

Output file:

`Data/customer_churn.parquet`

Parquet provides a structured and efficient format for storing the processed analytical dataset.

## 7. Customer Churn Definition

For this project, customer churn is defined as a customer cancelling their automatic subscription renewal.

The target variable is represented as follows:

| Churn Value | Meaning |
|---|---|
| 0 | Customer retained their subscription |
| 1 | Customer cancelled automatic renewal (churned) |

This definition is used consistently throughout the customer churn analysis.

## 8. Dashboard and Data Visualisation

The dashboard is developed using Python, Pandas and Matplotlib.

It presents important information about customer retention and subscription behaviour.

The dashboard includes the following visualisations:

### 8.1 Customer Churn Distribution

Compares the number of retained customers with the number of churned customers.

### 8.2 Churn Rate by Subscription Type

Examines how customer churn rates vary across different subscription categories.

### 8.3 Average Customer Complaints

Compares CRM complaint activity between retained and churned customers.

### 8.4 Customer Login Activity

Examines differences in website login activity between retained and churned customers.

### 8.5 Customer Satisfaction

Uses a box plot to compare customer satisfaction score distributions according to churn status.

### 8.6 Key Performance Indicators

The dashboard also presents four important KPIs:

- Total customers.
- Churned customers.
- Retained customers.
- Overall customer churn rate.

The final dashboard image is saved as:

`customer_churn_dashboard.png`

## 9. Installation and Requirements

The project requires Python and Jupyter Notebook.

The main Python dependencies can be installed using:

```bash
python -m pip install pandas numpy matplotlib boto3 pyarrow jupyter nbconvert
```

Additional dependencies may be required depending on the code used in the notebooks.

## 10. How to Run the Project

### 10.1 Set Up the Project

1. Clone or download the project repository.
2. Open the project folder in Visual Studio Code or another suitable Python environment.
3. Ensure Python is installed.
4. Install the required dependencies.
5. Make sure the required source datasets are available in the `Data/` directory.

### 10.2 Run the ETL Pipeline

1. Open `notebooks/ETL.ipynb`.
2. Review the extraction and transformation code.
3. Ensure the required database and CSV files are available.
4. Configure the university-provided storage credentials securely if the survey dataset needs to be downloaded again.
5. Execute the notebook cells in the correct order.
6. Check that the processed Parquet dataset is generated successfully.

Expected output:

`Data/customer_churn.parquet`

### 10.3 Run the Dashboard

1. Open `notebooks/Dashboard.ipynb`.
2. Ensure the ETL pipeline has generated the Parquet dataset.
3. Execute the notebook cells in order.
4. Review the customer churn KPIs.
5. Examine the dashboard visualisations.
6. Check that the dashboard image is generated successfully.

Expected output:

`customer_churn_dashboard.png`

### 10.4 Export Jupyter Notebooks to HTML

To export the notebooks into HTML format, execute the following commands from the project root directory:

```bash
python -m jupyter nbconvert --to html --output-dir=notebooks notebooks/ETL.ipynb
```

```bash
python -m jupyter nbconvert --to html --output-dir=notebooks notebooks/Dashboard.ipynb
```

## 11. Data Quality and Validation

Data validation is important to ensure that the processed dataset is suitable for customer churn analysis.

The project includes validation checks covering:

- Customer identifier uniqueness.
- Missing customer identifiers.
- Valid churn target values.
- Missing values in the processed dataset.
- Successful creation of the Parquet output.
- Successful generation of the dashboard image.

These checks help identify potential data quality issues during the ETL process.

## 12. Limitations

The dashboard provides descriptive analysis of customer behaviour. The visualisations identify patterns and associations but do not establish that a particular factor directly causes customer churn.

Other limitations include:

- Survey responses may be incomplete.
- Some customer records may contain missing information.
- The analysis depends on the quality of the supplied datasets.
- The findings are limited to the available data.
- Observed relationships should not automatically be interpreted as causal relationships.

The results should therefore be interpreted within the limitations of the available information.

## 13. Team Collaboration and Version Control

Git and GitHub are used to manage the project and support collaboration between team members.

The GitHub repository provides a shared location for authorised project files, documentation and other project resources.

The team can use Git to:

- Track changes to project files.
- Maintain a history of contributions.
- Share updates between team members.
- Review changes before integrating them.
- Collaborate on project development.
- Maintain a consistent version of the project.

Team members should regularly synchronise their local repositories with the shared GitHub repository to reduce conflicts.

## 14. Conclusion

The PerfectPetClub Customer Churn Analysis project demonstrates how data from multiple sources can be extracted, transformed and integrated into a structured analytical dataset.

The Python-based ETL pipeline prepares customer information for analysis, while the Matplotlib dashboard presents important customer retention indicators and behavioural patterns.

By examining subscription status, customer service interactions, login activity and satisfaction information, the project provides a descriptive understanding of customer churn.

The resulting analysis can help identify patterns that may support future customer retention strategies.

---

## Project Information

| Item | Details |
|---|---|
| Project | P3G7 – PerfectPetClub Customer Churn Analysis |
| Module | Data Engineering for Team Projects |
| University | University of Hertfordshire |
| Programming Language | Python |
| ETL Tool | Python and Pandas |
| Storage Format | Parquet |
| Visualisation | Matplotlib |
| Version Control | Git and GitHub |
>>>>>>> c38ef21 (Update project files, notebooks and dashboard)
