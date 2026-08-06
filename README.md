# Vehicle-Insurance-DataScience-MLOPS
# 🚗 End-to-End MLOps Project for Vehicle Insurance Prediction

Welcome to this **End-to-End MLOps Project**, designed to demonstrate a robust machine learning pipeline for **Vehicle Insurance Prediction**. This project showcases industry-standard MLOps practices, cloud deployment, automation, and software engineering principles used to build, train, evaluate, and deploy a production-ready machine learning application.

Whether you're a recruiter, hiring manager, or fellow developer, this repository highlights the complete lifecycle of a machine learning project—from project initialization and data ingestion to model deployment and automated CI/CD on AWS.

---
<img width="1920" height="1080" alt="App" src="https://github.com/user-attachments/assets/bea03ed7-5e8b-41ec-b651-cfaaf1a07714" />

# 🛠️ Tools & Technologies Used

This project leverages a modern MLOps technology stack to build, train, deploy, and automate a production-ready machine learning application.

| Category | Tools & Technologies |
|----------|----------------------|
| **Programming Language** | Python 3.10 |
| **Machine Learning** | Scikit-learn, NumPy, Pandas |
| **Data Visualization** | Matplotlib, Seaborn |
| **Web Framework** | FastAPI |
| **Frontend** | HTML5, CSS3, Jinja2 Templates |
| **Database** | MongoDB Atlas |
| **Cloud Platform** | Amazon Web Services (AWS) |
| **Cloud Services** | Amazon S3, Amazon EC2, Amazon ECR, AWS IAM |
| **Containerization** | Docker |
| **CI/CD** | GitHub Actions |
| **Version Control** | Git, GitHub |
| **Package Management** | pip, setup.py, pyproject.toml |
| **Environment Management** | Conda, Virtual Environment |
| **Configuration Management** | YAML |
| **Logging** | Python Logging Module |
| **Exception Handling** | Custom Exception Classes |
| **Serialization** | Pickle |
| **Development Environment** | Visual Studio Code, Jupyter Notebook |
| **Operating System** | Windows, Ubuntu Linux |
| **Deployment** | Docker Container on AWS EC2 |
| **Automation** | GitHub Self-Hosted Runner |


# 📁 Project Setup and Structure

## 📌 Step 1: Create Project Template

Execute the `template.py` file to automatically generate the project directory structure along with the required placeholder files.

---

## 📌 Step 2: Package Management

Configure the following files to enable importing local packages throughout the project.

- `setup.py`
- `pyproject.toml`

> **Note:** Refer to **crashcourse.txt** to understand how these files work.

---

## 📌 Step 3: Create Virtual Environment

Create a virtual environment.

```bash
conda create -n vehicle python=3.10 -y
```

Activate the environment.

```bash
conda activate vehicle
```

Install all project dependencies.

```bash
pip install -r requirements.txt
```

Verify the installed packages.

```bash
pip list
```

---

# 📊 MongoDB Setup and Data Management

## 📌 Step 4: MongoDB Atlas Configuration

- Create a MongoDB Atlas account.
- Create a new project.
- Deploy a free **M0 Cluster**.
- Configure the database username and password.
- Add the following IP address under **Network Access**.

```text
0.0.0.0/0
```

Retrieve the Python connection string and replace the placeholder password.

```text
mongodb+srv://<username>:<password>@cluster.mongodb.net/
```

---

## 📌 Step 5: Push Dataset to MongoDB

- Create a folder named `notebook`.
- Add the dataset.
- Create a notebook named `mongoDB_demo.ipynb`.
- Push the dataset into MongoDB Atlas.

Verify the uploaded records by navigating to:

```text
Database
    └── Browse Collections
```
<img width="1920" height="1080" alt="MongoDB" src="https://github.com/user-attachments/assets/fd45fe66-f9c6-415c-83ec-48fc5e7100d7" />

---

# 📝 Logging, Exception Handling & EDA

## 📌 Step 6: Logging & Exception Handling

Implement centralized

- Logging
- Custom Exception Handling

Validate both modules using

```text
demo.py
```

---

## 📌 Step 7: Exploratory Data Analysis (EDA)

Perform

- Data Cleaning
- Data Exploration
- Feature Engineering
- Visualization

inside the EDA notebook before moving to the machine learning pipeline.

---

# 📥 Data Ingestion

## 📌 Step 8: Data Ingestion Pipeline

Implement the Data Ingestion pipeline by:

- Configuring MongoDB connection inside `configuration.mongo_db_connections.py`
- Developing the data access layer
- Fetching data from MongoDB Atlas
- Transforming MongoDB documents into Pandas DataFrames
- Creating ingestion configuration and artifact classes
- Running the training pipeline

### Configure MongoDB Environment Variable

#### Bash

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>..."
```

#### PowerShell

```powershell
$env:MONGODB_URL="mongodb+srv://<username>:<password>..."
```

> **Windows Users:** You may also configure the environment variable through **System Environment Variables**.

---

# 🔍 Data Validation, Transformation & Model Training

## 📌 Step 9: Data Validation

Implement the Data Validation pipeline.

Tasks include:

- Schema Validation
- Missing Column Validation
- Data Type Validation
- Null Value Validation

Update the following files:

- `config/schema.yaml`
- `utils/main_utils.py`

---

## 📌 Step 10: Data Transformation

Implement feature engineering and preprocessing.

Create

```text
entity/estimator.py
```

Develop the transformation logic inside

```text
components/data_transformation.py
```

---

## 📌 Step 11: Model Training

Implement the complete model training pipeline.

The training component should

- Load transformed data
- Train machine learning models
- Select the best-performing model
- Save model artifacts

---

# 🌐 AWS Setup for Model Evaluation & Deployment

## 📌 Step 12: AWS Configuration

- Log in to AWS Console.
- Create an IAM User.
- Attach **AdministratorAccess** policy.
- Generate Access Keys.

Configure AWS credentials.

### Bash

```bash
export AWS_ACCESS_KEY_ID="YOUR_AWS_ACCESS_KEY_ID"
export AWS_SECRET_ACCESS_KEY="YOUR_AWS_SECRET_ACCESS_KEY"
```

### PowerShell

```powershell
$env:AWS_ACCESS_KEY_ID="YOUR_AWS_ACCESS_KEY_ID"
$env:AWS_SECRET_ACCESS_KEY="YOUR_AWS_SECRET_ACCESS_KEY"
```

Create an Amazon S3 Bucket.

```text
Bucket Name:
my-model-mlopsproj

Region:
us-east-1
```

Update the required AWS configurations inside

```text
constants/__init__.py
```

---

## 📌 Step 13: Model Evaluation & AWS S3 Model Registry

Develop the Model Evaluation component.

The pipeline should

- Compare the newly trained model with the production model.
- Push the best model to the AWS S3 Model Registry.

Implement AWS storage functionality inside

```text
src/aws_storage
```

and

```text
entity/s3_estimator.py
```

---

# 🚀 Model Evaluation, Model Pusher & Prediction Pipeline

## 📌 Step 14: Prediction Pipeline

Develop

- Model Evaluation
- Model Pusher
- Prediction Pipeline

Create the FastAPI application inside

```text
app.py
```

---

## 📌 Step 15: Web Interface

Create the following directories.

```text
static/
templates/
```

These directories are used for building the frontend interface using HTML, CSS, and Jinja2 Templates.

---

# 🔄 CI/CD Setup with Docker, GitHub Actions & AWS

## 📌 Step 16: Docker & GitHub Actions

Create

- `Dockerfile`
- `.dockerignore`

Configure GitHub Actions for Continuous Integration and Continuous Deployment.

Add the following GitHub Secrets.

```text
AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO
```
<img width="1920" height="1080" alt="Github (1)" src="https://github.com/user-attachments/assets/f49a14d9-7290-49b1-ae42-35dc33c156f8" />

<img width="1920" height="1080" alt="Github (2)" src="https://github.com/user-attachments/assets/b28e61fe-5b95-4231-856a-fe8b1dfc0f7a" />


---

## 📌 Step 17: AWS EC2 & Amazon ECR

Deploy the application on AWS.

Steps include:

- Create an EC2 Instance
- Install Docker
- Configure Amazon ECR
- Connect EC2 as a GitHub Self-Hosted Runner
- Automate deployment using GitHub Actions

---

## 📌 Step 18: Final Deployment

Open the application port on the EC2 Security Group.

```text
5000
```

Launch the application by visiting

```text
http://<public-ip>:5000
```

To start the training pipeline

```text
http://<public-ip>:5000/training
```

---



---

### 🔐 GitHub Secrets

Configure repository secrets to securely authenticate with AWS during CI/CD deployment.

---

# 🎯 Project Workflow Summary

```text
MongoDB Atlas
        │
        ▼
Data Ingestion
        │
        ▼
Data Validation
        │
        ▼
Data Transformation
        │
        ▼
Model Training
        │
        ▼
Model Evaluation
        │
        ▼
AWS S3 Model Registry
        │
        ▼
Prediction Pipeline
        │
        ▼
FastAPI Web Application
        │
        ▼
Docker
        │
        ▼
Amazon ECR
        │
        ▼
AWS EC2
        │
        ▼
GitHub Actions CI/CD
```
