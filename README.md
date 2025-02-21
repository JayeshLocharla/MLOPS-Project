# MLOPS-Project

# MLOPS-Project

The **MLOPS-Project** is a streamlined, production-ready workflow designed for deploying machine learning models with robust **CI/CD pipelines**, **MLflow tracking**, and **AWS integration**. This project follows a structured approach, starting with updating essential YAML configurations, refining pipeline components, and integrating the application (`app.py`) before deployment. 

The project ensures **version control, reproducibility, and scalability** in machine learning model deployment. It leverages **MLflow** for experiment tracking and model versioning, with **DagsHub** as the remote tracking server. Additionally, it integrates **AWS CI/CD pipelines** using GitHub Actions, automating the deployment process by:
1. Building a **Docker image** for the project.
2. Pushing the image to **AWS Elastic Container Registry (ECR)**.
3. Deploying the containerized application on an **AWS EC2 instance**.

With a **self-hosted GitHub runner**, the project automates model training, logging, and deployment, ensuring efficiency and reliability. The use of **AWS, Docker, and MLflow** makes this an ideal framework for **MLOps workflows**, providing scalability and seamless transitions from experimentation to production.


## Workflows

1. Update config.yaml
2. Update schema.yaml
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the app.py 



# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/JayeshLocharla/MLOPS-Project
```
### STEP 01- Create a conda environment after opening the repository

```bash
python3.8 -m venv mlprj
```

```bash
source mlprj/bin/activate
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```



## MLflow

[Documentation](https://mlflow.org/docs/latest/index.html)


##### cmd
- mlflow ui

### dagshub
[dagshub](https://dagshub.com/)

MLFLOW_TRACKING_URI=https://dagshub.com/locharlajayesh/MLOPS-Project.mlflow \
MLFLOW_TRACKING_USERNAME=locharlajayesh \
MLFLOW_TRACKING_PASSWORD=74b0c1ac0858f30152af127621a6753eccb2edb5 \
python script.py

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/locharlajayesh/MLOPS-Project.mlflow

export MLFLOW_TRACKING_USERNAME=locharlajayesh 

export MLFLOW_TRACKING_PASSWORD=74b0c1ac0858f30152af127621a6753eccb2edb5

```


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
    - Save the URI: 225989367359.dkr.ecr.us-east-2.amazonaws.com/mlprj

	
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

    AWS_ACCESS_KEY_ID

    AWS_SECRET_ACCESS_KEY

    AWS_REGION

    AWS_ECR_LOGIN_URI

    ECR_REPOSITORY_NAME



## About MLflow 
MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & tagging your model
