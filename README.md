# GovTech-Restaurant-Assessment
This project focuses on extracting, processing, and analyzing restaurant data from a JSON dataset, with a particular emphasis on events that took place in April 2019. The output is stored in CSV format, making it accessible for further analysis or integration with other systems.
## 1. Instructions on How to Run the Source Code Locally
### Prerequisites
- **Python 3.x** installed on your system.
- **pip** package manager to install dependencies.
- **Internet access** to download required data files.
### Installation
1. **Clone this Repository:**
```bash
git clone https://github.com/brendanchan03/GovTech-Restaurant-Assessment.git
cd GovTech-Restaurant-Assessment
```
2. **Set Up a Virtual Environment (Recommended):**
```bash
python -m venv venv
source venv/bin/activate # On Windows use: venv\Scripts\activate
```
### Running the Code
**Option 1: Using Jupyter Notebook**
1. Start Jupyter Notebook
2. Open main.ipynb in your browser.
3. Run all cells to execute the data processing steps, which will generate restaurants.csv and restaurant_events.csv in the project directory.
**Option 2: Running as a Python Script**
1. Convert the Jupyter notebook to a Python script:
```bash
jupyter nbconvert --to script main.ipynb
```
2. Execute the script:
```bash
python main.py
```
This will accomplish the same tasks as the notebook, producing the required CSV files.

## 2. Summary of Cloud Design and Deployment
### Design Overview
To deploy this solution on the cloud, a serverless architecture would be leveraged, focusing on scalability, cost-effectiveness, and ease of management.
### Data Ingestion:
- The input files (restaurant_data.json and country_codes.xlsx) would be stored in Amazon S3. S3 offers reliable, scalable storage, ensuring high availability of the data.
### Data Processing:
- AWS Lambda would be used for processing the data. Lambda's serverless nature automatically scales with demand and only incurs costs when the code is executed. This makes it a flexible and cost-efficient option for processing tasks.
- The Lambda function would extract relevant events from the dataset, specifically focusing on those in April 2019, and convert the results into CSV format.
### Storage and Access:
- The processed CSV files would be stored in a separate S3 bucket, enabling easy access for further processing or integration with other AWS services, such as AWS Athena or Amazon Redshift for querying and analysis.
### Deployment Considerations:
- **Scalability:** AWS Lambda scales automatically based on the load, ensuring that the solution can handle varying amounts of data without requiring manual intervention.
- **Cost Efficiency:** The serverless architecture minimizes costs, as expenses are only incurred when the Lambda function is running. S3 storage costs are also economical and scalable.
- **Security:** Access to S3 buckets would be tightly controlled using IAM roles and policies, ensuring that only authorized users and services can access the data.
### Decisions and Considerations
- **Serverless Architecture:** Using AWS Lambda in conjunction with S3 minimizes management overhead and automatically adjusts to handle workload variations.
- **Data Durability:** S3's durability ensures that data is safely stored and protected against loss.
- **Integration Flexibility:** S3 and Lambda can be easily integrated with other AWS services for more advanced processing, analytics, or even machine learning tasks.

## 3. Architecture Diagram
Below is a simplified architecture diagram illustrating the flow of data and the interaction between various components:
<div style="text-align: center;">
`````
+-------------------------+       +-------------------------+
|                         |       |                         |
|  Amazon S3 (Raw Data)   |       |  Amazon S3 (Processed)  |
|   - restaurant_data.json|<------|      - restaurants.csv  |
|   - country_codes.xlsx  |       |  - restaurant_events.csv|
|                         |       |                         |
+-------------------------+       +-------------------------+
            |                                  ^
            v                                  |
+-------------------------+       +-------------------------+
|                         |       |                         |
|   AWS Lambda            |<------|  AWS Lambda (Processing)|
|  (Data Ingestion)       |       |                         |
|                         |       |                         |
+-------------------------+       +-------------------------+
`````
</div>

- **Amazon S3 (Raw Data):** Stores the initial data files.
- **AWS Lambda (Data Processing):**  Extracts and processes the data to generate the final CSV files.
- **Amazon S3 (Processed Data):** Stores the output CSV files for further use.
This setup leverages AWS's serverless capabilities, ensuring that the solution is both scalable and cost-effective, while also being easy to manage and extend.