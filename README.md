# Medicaid Drug Rebate Program Analysis


## Project Overview



This project analyzes 195 newly reported Medicaid Drug Rebate Program (MDRP) package records published between July 27 and August 3, 2026. The analysis uses Python and pandas to clean the data, distinguish unique drug products from package configurations, examine regulatory classifications, and identify patterns in labeler reporting.


The project demonstrates exploratory data analysis, feature engineering, aggregation, data visualization, and interpretation of healthcare regulatory data.
 

## Business Questions

 

- Which labelers reported the most products and package configurations?

- How many unique products were represented by multiple packages?

- Which products had the greatest number of package configurations?

- How concentrated were submissions among the most active labelers?

- What were the distributions of therapeutic-equivalence codes, dispensing units, drug types, 5i classifications, and Covered Outpatient Drug statuses?

- How much time elapsed between products' coverage-effective dates and their reporting dates?



## Data Structure



The original dataset contains:



* **195 NDC11 records**: Individual package configurations

* **158 NDC9 records**: Unique drug products

* **58 labelers**

* **22 original variables**

# 

# Two identifiers were constructed during data cleaning:

# 

* **NDC9**: Combines the labeler and product segments to identify a unique drug product.

* **NDC11**: Combines the labeler, product, and package segments to identify a specific package configuration.

 Separating these identifiers prevents products with multiple package sizes from being counted as multiple distinct drugs.


## Key Findings



- The dataset contained 195 package configurations representing 158 unique products from 58 labelers.

- Chartwell Rx LLC reported the most products, with 14 products across 14 package configurations.

- Twenty-two labelers reported only one package, while 28 reported only one unique product.

- The five labelers reporting the most products accounted for 28.5% of all unique products.

- Thirty-three products appeared in more than one package configuration.

- One Avenacy Inc. product appeared in six package configurations, the highest number associated with a single NDC9.

- AB was the most common therapeutic-equivalence code, accounting for 55.7% of unique products.

- Tablets were the most common package unit, followed by milliliters, capsules, grams, individual units, and transdermal patches.

- Approximately 22.15% of unique products were classified as 5i drugs.

- Prescription drugs represented 90.51% of unique products, compared with 9.49% for over-the-counter drugs.

- More than 85% of unique products had Covered Outpatient Drug Status 01, indicating approval through an Abbreviated New Drug Application.

- Reporting-gap measurements were strongly right-skewed, showing that a relatively small number of products had much longer intervals between their coverage-effective and CMS reporting dates.

 

These findings describe one weekly reporting snapshot and should not be generalized as long-term MDRP patterns without analyzing additional reporting periods.



## Tools and Methods



- Python

- pandas

- Matplotlib

- Jupyter Notebook

- Data cleaning and type conversion

- NDC identifier construction

- Grouped aggregation

- Descriptive statistics

- Distribution analysis

- Date-difference analysis

- Data visualization



## Repository Structure



 ```text

 Medicaid-Drug-Rebate-Program-Analysis/

|-- data/

|   `-- healthcare\_data.csv

|-- product\_data\_healthcare.ipynb

|-- README.md

|-- requirements.txt

`-- .gitignore

```



## Running the Project



Clone the repository:


```bash

git clone https://github.com/Gjerm0x/Medicaid-Drug-Rebate-Program-Analysis.git

cd Medicaid-Drug-Rebate-Program-Analysis

```



Install the required packages:



```bash

pip install -r requirements.txt

```



Start Jupyter:



```bash

jupyter notebook

```



Open `product\_data\_healthcare.ipynb`, restart the kernel, and run all cells in order.



## Data Source



The analysis uses CMS data covering newly reported active covered outpatient drugs in the Medicaid Drug Rebate Program. The source files are weekly snapshots and are not updated to reflect subsequent changes.



[CMS Medicaid Drug Rebate Program Data](https://www.medicaid.gov/medicaid/prescription-drugs/medicaid-drug-rebate-program/medicaid-drug-rebate-program-data)



## Limitations



- The analysis covers only one weekly reporting period.

- Product and package counts measure reporting activity, not prescription volume, rebate value, or market share.

- Reporting gaps do not independently establish regulatory compliance or rebate eligibility.

- Patterns should be evaluated across additional weeks before being treated as stable trends.



## Future Development



- Automate ingestion of weekly CMS files.

- Track labeler concentration over time.

- Establish historical baselines for regulatory and product classifications.

- Monitor changes in reporting-gap distributions.

- Flag unusually large deviations for further review.

- Present the results through an interactive dashboard.

