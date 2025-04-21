# Refactoring-ML_Helathcare

## Table of Contents
- [Project Overview](#project-overview)
- [Key Client Requirements](#key-client-requirements)
- [System Architecture](#system-architecture)
- [Initial Development Contributions](#initial-development-contributions)
- [Class Diagram](#class-diagram)
- [Refactoring: Docker-based Deployment Enhancement](#refactoring-docker-based-deployment-enhancement)

## Project Overview

This project aims to predict the probability of developing **14 types of cancer and chronic diseases within 5 years** using health screening data from medical institutions.  
While the machine learning model was already developed, I was responsible for the **entire system design, development, and deployment** around it.  
As a personal project, I later refactored the system to enhance deployment and operational efficiency using Docker.

## Key Client Requirements

The client requested the following core features:

1. Model management (automated training and updates)
2. Disease probability prediction
3. PDF generation program
4. Automatic output of result PDFs

## System Architecture

The following diagram shows the overall structure of the system:

![image](https://github.com/user-attachments/assets/e0a37914-4d16-4eee-b059-194c702e08a0)

## Initial Development Contributions

**Tech Stack:**  
Python (PyQt, Flask) · Pandas/NumPy · MariaDB/MSSQL · HTML/CSS/JavaScript · FTP · Ubuntu

**Key Contributions:**

- Attended client meetings to **gather requirements**, and led the **system design and development**.
- Prevented two potential conflicts by **writing and version-controlling a requirements document**, clarifying the contract scope.
- Used **class and sequence diagrams** to organize the system architecture, improving code clarity and maintainability.
- Implemented a **lightweight automated system** using a Python scheduler to handle **model training, updates, and deployment**.
- Refactored parts of the data preprocessing logic from Python to SQL, **reducing execution time to 1/6**.
- Developed and integrated **16 web pages and a desktop application**, allowing intuitive visualization of predictions and **automatic PDF report generation**.
- Enabled error tracking through **logging**.

### Class Diagram

![image](https://github.com/user-attachments/assets/ea2beeed-6660-412c-9e20-5a0c5a2e0e14)


## Refactoring: Docker-based Deployment Enhancement

**Tools & Skills:**  
Docker · Docker Compose · Cron · Python · MSSQL

**Refactoring Highlights:**

- Refactored the system to improve deployment and maintenance for the 5-year disease prediction solution.
- Containerized a Flask-based ML auto-update system and MSSQL databases for scalable deployment.
- Eliminated memory leaks by replacing a persistent Python script with an OS-level cron scheduler.
- Implemented container orchestration and automated multi-service deployment using Docker Compose, enhancing operational efficiency.
- Set up Docker networking to enable seamless inter-container communication.
