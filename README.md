# TravelMemory — Highly Available & Scalable Full-Stack Web Application on AWS

## Project Overview
TravelMemory is a full-stack travel web application deployed on AWS using a highly available and scalable architecture.
The application allows users to view travel experiences and add new experiences. The frontend is built using React and the backend is developed using Node.js and MongoDB Atlas is used as the database.
The main objective of this mini project was to deploy the application end-to-end on AWS, create reusable Amazon Machine Images (AMIs), scale both the frontend and backend tiers to two EC2 instances, and place each tier behind its own Application Load Balancer (ALB) to improve availability, scalability, and reliability.

## Key AWS concepts demonstrated
•	Amazon EC2
•	Amazon AMI
•	Application Load Balancer (ALB)
•	Target Groups
•	Security Groups
•	Amazon VPC / Subnets
•	Nginx
•	systemd
•	MongoDB Atlas
•	React production build
•	Node.js backend
•	High availability and horizontal scaling
## Final Architecture

![TravelMemory Architecture](images/1.png)

![TravelMemory Architecture](images/2.png)

## MongoDB Atlas Setup
![TravelMemory Architecture](images/3.png)

## Launch Backend Master EC2
     Create the first backend server.
## Configuration
•	Name: backend-master
•	OS: Ubuntu 22.04
•	Instance type: free-tier eligible instance
•	SSH key: existing AWS key pair
## Security Group
![TravelMemory Architecture](images/sg.png)
## Required access:
   Port	Purpose
   22	SSH
   80	HTTP (Nginx)
   3000	Backend (Node app, for direct testing)

## Connect to the server:
ssh -i <key-file>.pem ubuntu@<backend-master-public-ip>

## Launch Backend master

![TravelMemory Architecture](images/4.png)
![TravelMemory Architecture](images/5.png)
## Update Ubuntu :

   sudo apt update
![TravelMemory Architecture](images/6.png)

## Install Node.js, npm, Git and Nginx
sudo apt install -y nodejs npm git nginx


![TravelMemory Architecture](images/7.png)


## Clone TravelMemory
git clone https://github.com/UnpredictablePrashant/TravelMemory.git

![TravelMemory Architecture](images/8.png)
![TravelMemory Architecture](images/9.png)
![TravelMemory Architecture](images/10.png)
![TravelMemory Architecture](images/11.png)

# Backend application is working

Create systemd Service 
![TravelMemory Architecture](images/12.png)

# Configure Nginx
Test Nginx Configuration

![TravelMemory Architecture](images/13.png)
![TravelMemory Architecture](images/14.png)

# Test Backend

![TravelMemory Architecture](images/15.png)

# Create Frontend Master :

![TravelMemory Architecture](images/16.png)
![TravelMemory Architecture](images/17.png)

Install Node.js, npm, Git and Nginx

![TravelMemory Architecture](images/18.png)
![TravelMemory Architecture](images/19.png)
![TravelMemory Architecture](images/20.png)

# Test Frontend
![TravelMemory Architecture](images/21.png)

# Frontend Master is also working successfully
# Create Frontend and BACKEND AMI

![TravelMemory Architecture](images/22.png)

# Launch instance #2 from each AMI :

![TravelMemory Architecture](images/23.png)

# Test Backend-2
![TravelMemory Architecture](images/24.png)

# Backend Target Group
![TravelMemory Architecture](images/25.png)

# BACKEND Application Load Balancer
![TravelMemory Architecture](images/26.png)

# Test Backend ALB

![TravelMemory Architecture](images/27.png)

# Backend ALB is working
![TravelMemory Architecture](images/28.png)

# Launch Frontend-2 instance:
![TravelMemory Architecture](images/29.png)

# Frontend Target Group
![TravelMemory Architecture](images/30.png)

# FRONTEND Load Balancer
![TravelMemory Architecture](images/31.png)

# Test frontend ALB
![TravelMemory Architecture](images/32.png)
Frontend is also ALB working

# Connect Frontend to Backend ALB
![TravelMemory Architecture](images/33.png)

# Verify Data in MongoDB Atlas

![TravelMemory Architecture](images/34.png)
![TravelMemory Architecture](images/35.png)

# DNS Setup
![TravelMemory Architecture](images/36.png)
![TravelMemory Architecture](images/37.png)

## 🎉 TravelMemory AWS Deployment — Successfully Completed ✅

The application was tested successfully through the final domain.
Existing travel experiences were displayed and new experiences could be added successfully.
MongoDB Atlas was also verified as the persistent database layer.

![TravelMemory Architecture](images/38.png)
![TravelMemory Architecture](images/39.png)



