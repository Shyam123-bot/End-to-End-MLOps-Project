Here’s a **concise, professional, and informative README** for your project:

---

# 🚀 **End-to-End ML Pipeline with CI/CD and Deployment**

This project demonstrates the complete lifecycle of a Machine Learning pipeline, from data preparation to model deployment, using **MLflow**, **Flask**, **Docker**, and **AWS**. It integrates modern **MLOps** practices, including **CI/CD**, for seamless development and deployment.

---

## 🎯 **Project Highlights**

### ✅ **Key Features**
- **Experiment Tracking**: Track hyperparameters, metrics, and artifacts using MLflow.
- **Model Training**: Automated pipelines for model training, evaluation, and saving.
- **API Integration**: Flask API for real-time predictions and a user-friendly web interface.
- **Containerization**: Dockerized application for easy portability and scalability.
- **CI/CD Pipeline**: Fully automated deployment pipeline using GitHub Actions.
- **Cloud Deployment**: Deployed on AWS using EC2 and ECR for Docker image management.
- **Robust Engineering**: Logging and error handling for reliability in production.

---

## 🛠️ **Tech Stack**
- **Programming Language**: Python  
- **Frameworks**: Flask, Scikit-learn  
- **MLOps Tools**: MLflow, Docker  
- **Cloud Services**: AWS EC2, AWS ECR  
- **CI/CD**: GitHub Actions  
- **Version Control**: Git  

---

## 📂 **Project Structure**
```
.
├── src/
│   ├── pipeline/
│   │   ├── data_ingestion.py
│   │   ├── data_validation.py
│   │   ├── model_training.py
│   │   ├── model_evaluation.py
│   │   ├── prediction.py
│   │   └── __init__.py
│   ├── utils/
│   ├── app.py  # Flask app
│   └── config/
├── Dockerfile
├── requirements.txt
├── README.md
└── .github/
    └── workflows/
        └── main.yml  # CI/CD Pipeline
```

---

## ⚙️ **Setup and Installation**

### Prerequisites
- Python >= 3.8
- Docker
- AWS CLI

### Steps
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application Locally**:
   ```bash
   python src/app.py
   ```

4. **Build Docker Image**:
   ```bash
   docker build -t ml-project .
   ```

5. **Run Docker Container**:
   ```bash
   docker run -p 8080:8080 ml-project
   ```

---

## 🚀 **Deployment**

### CI/CD with GitHub Actions
- Push code changes to the main branch to trigger the CI/CD workflow.
- The workflow:
  - Builds and pushes Docker images to AWS ECR.
  - Deploys the containerized application to AWS EC2.

### AWS Services Used:
- **ECR**: Elastic Container Registry to manage Docker images.
- **EC2**: Elastic Compute Cloud for hosting the application.

---

## 📊 **How to Use**
1. Access the Flask web interface via the deployed URL or `localhost:8080`.
2. Use the form to input features and predict results.
3. Check experiment details in the MLflow UI.

# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.ap-south-1.amazonaws.com/mlproj

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app
---

## 🚧 **Future Enhancements**
- Add Kubernetes for orchestration.
- Implement advanced hyperparameter tuning.
- Include real-time monitoring with Prometheus and Grafana.

