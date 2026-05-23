# 🚗 Vehicle Insurance Prediction — MLOps Pipeline

> An end-to-end production-ready Machine Learning system with CI/CD, Docker & AWS deployment

[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-blue?logo=github-actions)](https://github.com/nogiayash/MLOPS-proj1/actions)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://www.docker.com/)
[![AWS](https://img.shields.io/badge/AWS-EC2%20%7C%20ECR%20%7C%20S3-FF9900?logo=amazon-aws)](https://aws.amazon.com/)
[![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-API-009688?logo=fastapi)](https://fastapi.tiangolo.com/)


---

## 📌 Problem Statement

Insurance companies need to identify customers likely to purchase vehicle insurance to optimize marketing strategies and reduce operational costs.

**Manual approaches are:**
- ❌ Time-consuming
- ❌ Not scalable
- ❌ Inconsistent

**👉 This project builds a production-ready MLOps pipeline that automates:**
- ✅ Data ingestion
- ✅ Model training
- ✅ Deployment
- ✅ Real-time predictions

---

## 🎯 Key Highlights

| Feature | Status |
|---|---|
| End-to-End ML Pipeline | ✅ |
| MongoDB-based Data Ingestion | ✅ |
| SMOTE for Class Imbalance | ✅ |
| CI/CD with GitHub Actions | ✅ |
| Dockerized Deployment | ✅ |
| AWS (S3 + EC2 + ECR) Integration | ✅ |
| FAST API + Web UI | ✅ |

---

## 🏗️ Architecture

<img width="1774" height="887" alt="Vehicle Insurance Architecture" src="https://github.com/user-attachments/assets/f4dbe6e5-0d17-4b31-b0d2-0a77bc1ba2d1" />


---

## 📊 Model Performance

To handle class imbalance, **SMOTE** (Synthetic Minority Oversampling Technique) was applied before training.

**Model used:** Random Forest Classifier

| Metric | Score |
|---|---|
| Precision | 0.881 |
| Recall | 0.930 |
| F1 Score | 0.904 |

### 🔍 Insights

- **High Recall (0.93)** ensures most potential customers are correctly identified
- **Slightly lower Precision** indicates manageable false positives
- **Strong F1 Score** shows balanced overall performance

> ⚠️ **Note:** The high recall is influenced by SMOTE. Evaluation was done on a separate test set to avoid data leakage.

---

## 📸 Application Demo

### 🔹 Web Interface

<img width="1500" height="812" alt="image" src="https://github.com/user-attachments/assets/979f7f90-1241-4c60-a772-560237962a87" />


> Users can input customer details and get real-time insurance prediction results.

---

## ⚙️ CI/CD Pipeline

Automated using **GitHub Actions** with two stages:

### 🔷 Continuous Integration

<img width="1568" height="742" alt="image" src="https://github.com/user-attachments/assets/25fe2e56-eda1-4e59-aa0d-ca562cac3827" />


### 🔷 Continuous Deployment

<img width="1568" height="672" alt="image" src="https://github.com/user-attachments/assets/3f76a498-103b-46a1-a1ad-07dbb0066e51" />


**Pipeline flow:**

1. Code pushed to GitHub
2. Docker image built
3. Image pushed to AWS ECR
4. Deployed on EC2 instance
5. Application served via container

---

## 🐳 Docker Usage

```bash
docker build -t vehicle-mlops .
docker run -p 5000:5000 vehicle-mlops
```

---

## ☁️ AWS Deployment

| Service | Purpose |
|---|---|
| **AWS S3** | Model artifact storage |
| **AWS ECR** | Docker image registry |
| **AWS EC2** | Application hosting |

> ⚠️ **Note:** AWS resources have been terminated to avoid costs, but the project is fully deployable using the provided pipeline.

---

## 🔌 API Usage

**Endpoint:**
```
POST /predict
```

**Request:**
```json
{
  "Gender": 1,
  "Age": 35,
  "Driving_License": 1,
  "Region_Code": 28,
  "Previously_Insured": 0,
  "Annual_Premium": 30000,
  "Policy_Sales_Channel": 26,
  "Vintage": 120,
  "Vehicle_Age_1_2_Year": 1,
  "Vehicle_Damage_Yes": 1
}
```

**Response:**
```json
{
  "prediction": "Interested"
}
```

---

## 📂 Project Structure

```
MLOPS-proj1/
├── src/
│   ├── components/         # Data ingestion, transformation, training
│   ├── pipeline/           # Training and prediction pipelines
│   ├── entity/             # Config and artifact entities
│   ├── config/             # Configuration management
│   └── aws_storage/        # S3 interaction utilities
│
├── notebook/               # EDA and experimentation
├── templates/              # HTML templates for Fast API UI
├── static/                 # CSS/JS assets
├── app.py                  # entry point (Creating/Running Fast API web server) 
├── Dockerfile              # Container definition
└── requirements.txt        # Python dependencies
```

---

## 🧪 Run Locally

```bash
# Create and activate environment
conda create -n vehicle python=3.10 -y
conda activate vehicle

# Install dependencies
pip install -r requirements.txt

# Start the application
python app.py
```

---

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```env
MONGODB_URL=your_mongodb_url
AWS_ACCESS_KEY_ID=your_key
AWS_SECRET_ACCESS_KEY=your_secret
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.10 |
| ML Framework | Scikit-learn |
| Imbalance Handling | imbalanced-learn (SMOTE) |
| Web Framework | Fast API |
| Database | MongoDB Atlas |
| Containerization | Docker |
| CI/CD | GitHub Actions |
| Cloud | AWS (S3, EC2, ECR) |

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">Made with ❤️ by <a href="https://github.com/nogiayash">nogiayash</a></p>
