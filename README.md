# 🚗 Vehicle Classification MLOps Project

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/downloads/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green.svg)](https://www.mongodb.com/atlas)
[![AWS](https://img.shields.io/badge/AWS-Cloud-orange.svg)](https://aws.amazon.com/)
[![Docker](https://img.shields.io/badge/Docker-Containerized-blue.svg)](https://www.docker.com/)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-yellowgreen.svg)](https://github.com/features/actions)

## 🎯 Project Overview

A comprehensive **end-to-end MLOps pipeline** for vehicle classification that demonstrates modern machine learning operations practices. This project showcases the complete ML lifecycle from data ingestion to model deployment with automated CI/CD pipelines, cloud infrastructure, and containerized deployment.

## 🏗️ Architecture & Tech Stack

### **Core Technologies**
- **Language**: Python 3.10
- **Database**: MongoDB Atlas (NoSQL)
- **Cloud Provider**: AWS (S3, EC2, ECR, IAM)
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Web Framework**: Flask
- **Package Management**: Conda + pip

### **MLOps Components**
```mermaid
graph LR
    A[Data Ingestion] --> B[Data Validation]
    B --> C[Data Transformation]
    C --> D[Model Training]
    D --> E[Model Evaluation]
    E --> F[Model Pusher]
    F --> G[Prediction Pipeline]
    G --> H[Web Application]
```

## 🚀 Key Features

### ✨ **Advanced MLOps Practices**
- **Modular Pipeline Design**: Component-based architecture with clear separation of concerns
- **Configuration Management**: Centralized configuration with YAML schemas
- **Artifact Management**: Systematic tracking of data and model artifacts
- **Cloud-Native Architecture**: Leverages AWS services for scalability and reliability

### 🔧 **Production-Ready Components**
- **Custom Exception Handling**: Comprehensive error management system
- **Advanced Logging**: Structured logging with multiple levels and file rotation
- **Data Validation**: Schema-based validation with automated drift detection
- **Model Registry**: S3-based model versioning and management

### ☁️ **Cloud Infrastructure**
- **MongoDB Atlas**: Managed NoSQL database for data storage
- **AWS S3**: Model registry and artifact storage
- **AWS EC2**: Production deployment environment
- **AWS ECR**: Container image repository
- **IAM**: Secure access management

## 📁 Project Structure

```
vehicle-classification-mlops/
├── 📂 src/
│   ├── 📂 components/           # ML pipeline components
│   ├── 📂 configuration/       # Database and cloud connections
│   ├── 📂 constants/           # Project constants and configs
│   ├── 📂 data_access/         # Data retrieval and management
│   ├── 📂 entity/              # Data models and schemas
│   ├── 📂 pipeline/            # Training and prediction pipelines
│   └── 📂 utils/               # Utility functions and helpers
├── 📂 notebook/                # EDA and feature engineering
├── 📂 static/                  # Web application assets
├── 📂 templates/               # HTML templates
├── 📂 .github/workflows/       # CI/CD pipeline definitions
├── 📄 app.py                   # Flask web application
├── 📄 Dockerfile              # Container configuration
├── 📄 requirements.txt         # Python dependencies
├── 📄 setup.py                 # Package installation
└── 📄 pyproject.toml          # Modern Python packaging
```

## 🛠️ Installation & Setup

### **1. Environment Setup**
```bash
# Create and activate virtual environment
conda create -n vehicle python=3.10 -y
conda activate vehicle

# Install dependencies
pip install -r requirements.txt

# Verify local package installation
pip list
```

### **2. Database Configuration**
```bash
# Set MongoDB connection (Choose your platform)

# For Bash/Linux/MacOS
export MONGODB_URL="mongodb+srv://username:password@cluster.mongodb.net/"

# For PowerShell
$env:MONGODB_URL = "mongodb+srv://username:password@cluster.mongodb.net/"

# For Windows Environment Variables
# Add MONGODB_URL to system environment variables
```

### **3. AWS Configuration**
```bash
# Configure AWS credentials (Choose your platform)

# For Bash/Linux/MacOS
export AWS_ACCESS_KEY_ID="your_access_key"
export AWS_SECRET_ACCESS_KEY="your_secret_key"

# For PowerShell
$env:AWS_ACCESS_KEY_ID="your_access_key"
$env:AWS_SECRET_ACCESS_KEY="your_secret_key"
```

## 🔄 MLOps Pipeline Workflow

### **Data Pipeline**
1. **📥 Data Ingestion**: Automated data extraction from MongoDB Atlas
2. **✅ Data Validation**: Schema validation and data quality checks
3. **🔄 Data Transformation**: Feature engineering and preprocessing
4. **🎯 Model Training**: ML model development with hyperparameter tuning

### **Model Pipeline**
5. **📊 Model Evaluation**: Performance assessment with threshold-based validation
6. **☁️ Model Pusher**: Automated model deployment to S3 registry
7. **🔮 Prediction Pipeline**: Real-time inference capability
8. **🌐 Web Application**: User-friendly interface for predictions

## 🚀 Deployment & CI/CD

### **Containerization**
- **Docker**: Multi-stage builds for optimized container images
- **AWS ECR**: Secure container registry with automated pushes

### **Continuous Integration/Deployment**
- **GitHub Actions**: Automated testing, building, and deployment
- **Self-Hosted Runners**: EC2-based runners for seamless AWS integration
- **Blue-Green Deployment**: Zero-downtime deployment strategy

### **Infrastructure**
- **AWS EC2**: Production server with auto-scaling capabilities
- **Security Groups**: Configured for secure web traffic (ports 5080)
- **IAM Roles**: Least-privilege access management

## 📈 Model Management

### **Model Registry**
- **Versioning**: Systematic model versioning with S3 storage
- **Artifact Tracking**: Complete lineage from data to deployed model
- **Performance Monitoring**: Continuous model performance evaluation
- **Rollback Capability**: Easy model rollback for production stability

### **Evaluation Metrics**
- **Threshold-Based Validation**: Automated model promotion based on performance
- **A/B Testing Ready**: Infrastructure supports comparative model testing
- **Drift Detection**: Automated detection of data and model drift

## 🌐 Web Application

### **Features**
- **Real-time Predictions**: Instant vehicle classification
- **Model Training Interface**: On-demand model retraining via `/training` endpoint
- **Performance Dashboard**: Model metrics and system health
- **Responsive Design**: Mobile-friendly interface

### **Endpoints**
- `GET /`: Main prediction interface
- `POST /predict`: Vehicle classification API
- `GET /training`: Trigger model retraining
- `GET /health`: System health check

## 📊 Monitoring & Observability

### **Logging System**
- **Structured Logging**: JSON-formatted logs for better parsing
- **Log Levels**: DEBUG, INFO, WARNING, ERROR, CRITICAL
- **File Rotation**: Automated log file management
- **Centralized Logging**: All components log to unified system

### **Exception Handling**
- **Custom Exceptions**: Domain-specific error handling
- **Error Tracking**: Comprehensive error logging and notification
- **Graceful Degradation**: System continues operation during partial failures

## 🔧 Development Workflow

### **Local Development**
```bash
# Run the application locally
python app.py

# Access the application
http://localhost:5000
```

### **Testing**
```bash
# Run unit tests
python -m pytest tests/

# Run integration tests
python -m pytest tests/integration/
```

### **Model Training**
```bash
# Trigger training pipeline
python demo.py

# Or via web interface
curl -X GET http://localhost:5000/training
```

## 📚 Key Learnings & Best Practices

### **MLOps Best Practices Implemented**
- ✅ **Version Control**: Git-based versioning for code, data, and models
- ✅ **Reproducibility**: Containerized environments and dependency locking
- ✅ **Scalability**: Cloud-native architecture with auto-scaling capabilities
- ✅ **Monitoring**: Comprehensive logging and performance tracking
- ✅ **Security**: IAM-based access control and secret management
- ✅ **Testing**: Automated testing in CI/CD pipeline
- ✅ **Documentation**: Comprehensive documentation and code comments

### **Production Readiness Features**
- 🔒 **Security**: Encrypted connections and secure credential management
- 📊 **Scalability**: Horizontally scalable architecture
- 🔄 **Reliability**: Fault-tolerant design with graceful error handling
- 📈 **Performance**: Optimized for low-latency predictions
- 🔍 **Observability**: Complete system monitoring and alerting

## 🏆 Project Highlights

### **Technical Achievements**
- **End-to-End Automation**: Complete ML pipeline automation from data to deployment
- **Cloud-Native Design**: Leverages managed services for scalability and reliability
- **Modern DevOps**: Implements current industry standards and best practices
- **Production Deployment**: Real-world deployment on AWS infrastructure

### **Business Value**
- **Reduced Time-to-Market**: Automated pipelines accelerate model deployment
- **Cost Optimization**: Efficient resource utilization with cloud services
- **Risk Mitigation**: Comprehensive testing and validation reduce production issues
- **Scalability**: Architecture supports business growth and increased demand

## 🎯 Future Enhancements

- [ ] **MLflow Integration**: Enhanced experiment tracking and model registry
- [ ] **Kubernetes Deployment**: Container orchestration for better scalability
- [ ] **Real-time Monitoring**: Grafana/Prometheus integration for metrics
- [ ] **Feature Store**: Centralized feature management and sharing
- [ ] **Model Explainability**: SHAP/LIME integration for model interpretability

---

## 👨‍💻 About the Developer

This project demonstrates proficiency in:
- **MLOps Engineering**: End-to-end ML pipeline development
- **Cloud Architecture**: AWS services integration and management
- **DevOps Practices**: CI/CD, containerization, and infrastructure as code
- **Software Engineering**: Clean code, testing, and documentation
- **Data Engineering**: ETL pipelines and data quality management

*Ready to bring these skills to your team and drive ML initiatives forward!*

---

<div align="center">
  <strong>⭐ If you found this project valuable, please give it a star! ⭐</strong>
</div>