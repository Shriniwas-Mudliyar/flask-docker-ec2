# Dockerized Flask App on AWS EC2

## Project Overview
This project demonstrates deploying a Flask web application in a Docker container on AWS EC2. The app displays a simple message and showcases containerization, cloud deployment, and Linux server setup.

## Architecture

Local PC
↓
GitHub Repository
↓
AWS EC2 (Amazon Linux)
→ Docker
→ Flask Container (Port 5000 mapped to 80)



## Technologies Used
- Python 3 & Flask
- Docker
- Amazon EC2 (Amazon Linux)
- Git & GitHub

## Setup Instructions

### Local Setup
1. Clone the repository:
git clone https://github.com/Shriniwas-Mudliyar/flask-docker-ec2.git
cd flask-docker-ec2


Build Docker image:

docker build -t flask-app .


Run container locally:

docker run -d -p 5000:5000 flask-app


Open http://localhost:5000 in your browser to see the app.

Deployment on AWS EC2

Launch Amazon Linux 2 EC2 instance with a key pair.

Allow inbound traffic for SSH (22), HTTP (80), and TCP 5000.

SSH into EC2:

ssh -i flask-key.pem ec2-user@EC2_PUBLIC_IP


Install Docker and Git:

sudo yum update -y
sudo yum install docker git -y
sudo systemctl start docker
sudo usermod -aG docker ec2-user


Clone repository:

git clone https://github.com/Shriniwas-Mudliyar/flask-docker-ec2.git
cd flask-docker-ec2


Build Docker image:

docker build -t flask-app .


Run container:

docker run -d -p 80:5000 flask-app


Open http:// in your browser to access the live app.

Screenshots:

<img width="1920" height="1080" alt="Screenshot 2026-01-30 170643" src="https://github.com/user-attachments/assets/f8bd40d0-d7b7-42e4-b3fd-3ed7f38551b2" />

<img width="1920" height="1080" alt="Screenshot 2026-01-30 170634" src="https://github.com/user-attachments/assets/89dfe3f6-e2e3-41ba-bfdf-7437e391c5fc" />

<img width="1918" height="1079" alt="Screenshot 2026-01-30 170515" src="https://github.com/user-attachments/assets/fed71aa5-c7c9-4158-9cf8-b26ed82d16c5" />

What I Learned

Creating Dockerfile and containerizing a Flask app

Deploying Docker containers on AWS EC2

Linux server configuration and management

Mapping container ports for public access

GitHub version control and project documentation

