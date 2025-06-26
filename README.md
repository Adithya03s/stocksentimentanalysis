# stocksentimentanalysis
📊 Stock Sentiment Analysis Dashboard 

This project implements a serverless, cloud-native pipeline to analyze stock sentiment and visualize it using a Streamlit dashboard deployed via AWS ECS Fargate. The data is collected daily from a stock API, analyzed for sentiment, and stored in Amazon RDS and S3. A Streamlit dashboard allows users to visualize and explore the sentiment trends.

🔁 Pipeline Workflow:

1. **Trigger (EventBridge):**
   - Scheduled to run **daily**
   - Invokes an AWS Lambda function

2. **Processing (AWS Lambda):**
   - Fetches data from a **Stock API**
   - Performs **sentiment analysis**
   - Stores:
     - Processed sentiment data → **Amazon RDS (PostgreSQL)**
     - Raw stock data in JSON format → **Amazon S3**

3. **Data Storage:**
   - **Amazon RDS:** Structured data with sentiment scores
   - **Amazon S3:** Backup of raw stock API responses

4. **Dashboard Deployment:**
   - Dashboard developed locally using **Streamlit**
   - Containerized with **Docker**
   - Image pushed to **Amazon ECR**
   - Deployed to **Amazon ECS Fargate**
   - Accessed via browser on **port 8051**


📁 Architecure Diagram

![stocksentimentanalysis](stockarch.jpeg)

 
🚀 Features

- Daily automated data pipeline using AWS EventBridge and Lambda
- Sentiment analysis on stock data
- Storage in both PostgreSQL (Amazon RDS) and Amazon S3
- Streamlit dashboard built with Python and deployed via ECS Fargate
- Easily accessible via a browser on port 8051



🛠️ Technologies Used

| Technology        | Purpose                              |
|-------------------|---------------------------------------|
| AWS Lambda        | Serverless stock processing logic     |
| AWS EventBridge   | Daily trigger scheduler               |
| Amazon RDS (PostgreSQL) | Structured data store            |
| Amazon S3         | Raw JSON backup of stock data         |
| Amazon ECS Fargate| Hosting the Streamlit dashboard       |
| Amazon ECR        | Docker image registry                 |
| Streamlit         | Web-based interactive dashboard       |
| Docker            | Containerization of the dashboard     |
| Python            | Primary language for Lambda + frontend|
