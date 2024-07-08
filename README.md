# Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment

This repository consists of two main parts. In the first part, we apply deep learning to our classification task using various deep learning models to identify the best-performing model. In the second part, we focus on deploying this deep learning model to the cloud, enabling easy access for everyone. For deployment, we utilize a CI/CD pipeline and an EC2 instance server.

The AWS Cloud Deployment Part was followed from @krishnaik06 Sir's Youtube Channel and you can find that repository here Kidney-Disease-Classification-Deep-Learning-Project

## Part-1: Kidney Disease Classification using Deep Learning Architectures
You can find these code file under the folder Part-1-DeepLearningArchitectures-CNN+ResNet18+SqueezeNet

### Dataset Overview:
https://www.kaggle.com/datasets/nazmul0087/ct-kidney-dataset-normal-cyst-tumor-and-stone
![image](https://github.com/Akshayaa-bk/Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment/assets/116330039/03a1071b-2383-4ac7-b427-96aefa98477a)


### Methodology:
![image](https://github.com/Akshayaa-bk/Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment/assets/116330039/0c85c578-a914-4674-96f3-0335fbc62bb6)



### Simulation Architecture:

#### Platform & Tools

#### Library
- PyTorch

#### Platform
 - Kaggle
   
#### Hardware
-P100 GPU acceleration

#### Hyperparameters
Optimizer: ADAM
Learning Rate: 0.001
Batch size: 32
Training Parameters
Epochs: 100
Dropout Value: 0.5

### Best Model Results:
Out of the 3 models which have we have Implemented, ResNet18 have achieved an highest accuracy of 99.92%. You can see the Validation Loss and Accuracy plots along with the t-SNE plots below.


![image](https://github.com/Akshayaa-bk/Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment/assets/116330039/64c9410e-11b5-4e4e-8524-68da6ba1c2dd)


![image](https://github.com/Akshayaa-bk/Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment/assets/116330039/b2357581-6520-4cc1-b59b-8537f20b9efd)


## Part-2: Deployment in AWS Cloud using CI/CD Pipeline in EC2

### User Interface:

![image](https://github.com/Akshayaa-bk/Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment/assets/116330039/1709d99c-e07e-4c2d-a828-337e3cd9b47b)

![image](https://github.com/Akshayaa-bk/Kidney-Disease-Detection-using-Deep-Learning-Architectures-and-AWS-Cloud-Deployment/assets/116330039/e504143d-d7a8-4487-a1e6-04d8e880e392)

### Workflows

- Update config.yaml
- Update secrets.yaml [Optional]
- Update params.yaml
- Update the entity
- Update the configuration manager in src config
- Update the components
- Update the pipeline
- Update the main.py
- Update the dvc.yaml
- app.py

  
##How to run?

STEPS:
Clone the repository
[https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning.git](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning.git)

### STEP 01- Create a conda environment after opening the repository
conda create -n kidney python=3.8 -y
conda activate kidney

### STEP 02- install the requirements
pip install -r requirements.txt
# Finally run the following command
python app.py

Now,
open up you local host and port

#### DVC cmd
dvc init
dvc repro
dvc dag


### About MLflow & DVC
MLflow

Its Production Grade
Trace all of your expriements
Logging & taging your model
DVC

Its very lite weight for POC only
lite weight expriements tracker
It can perform Orchestration (Creating Pipelines)


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


### 3. Create ECR repo to store/save docker image
- Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/chicken
- 
### 4. Create EC2 machine (Ubuntu)

### 5. Open EC2 and Install docker in EC2 Machine:
#optinal

sudo apt-get update -y

sudo apt-get upgrade

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker

### 6. Configure EC2 as self-hosted runner:
setting>actions>runner>new self hosted runner> choose os> then run command one by one

### 7. Setup github secrets:
AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = us-east-1

AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

ECR_REPOSITORY_NAME = simple-app


