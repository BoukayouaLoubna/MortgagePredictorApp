# MortgagePredictorApp
# Mortgage Prepayment Forecasting Application

This repository contains a Flask-based web application designed for forecasting mortgage prepayment and delinquency risks.  
It leverages a pre-trained machine learning model to process various mortgage-related attributes for classification and regression predictions.

## Table of Contents
- Overview
- System Design
- Highlights
- Installation and Setup
- Application Workflow
- User Inputs
- Debugging and Logs
- Machine Learning Model Details
- Contribution Guide
- Licensing Information

## Overview
This application provides predictions on mortgage loans using features such as borrower demographics, loan characteristics, and historical mortgage performance.  
It supports both classification (risk prediction) and regression (quantitative analysis) models.

## System Design

![image](https://github.com/user-attachments/assets/01205017-0684-4cc4-bfe0-15ab2a0e11f9)

## Background workflow

![image](https://github.com/user-attachments/assets/4f51ef3e-9990-40c0-a3e9-456e353e19cd)

## Highlights
- A user-friendly interface for inputting mortgage loan details.
- A Flask backend processes inputs and returns prediction results.
- Validation checks ensure correct input formatting.
- Logging system to capture user interactions and detect errors.
- A pre-trained scikit-learn machine learning model is used for predictions.

## Installation and Setup

### Prerequisites
Ensure the following software and libraries are installed:
- Python 3.x
- Flask framework
- scikit-learn
- pandas
- joblib
- HTML template engine

### Clone the Repository
```bash
git clone https://github.com/yourusername/mortgage-prepayment-forecasting.git
cd mortgage-prepayment-forecasting
```

### Install Dependencies
Use the command below to install all required packages:
```bash
pip install -r requirements.txt
```

### Load Pre-trained Model
Download the pre-trained model file `mortgage_pipeline_model_.pkl` and place it inside the `models/` folder.

### Start the Application
Run the application with:
```bash
python app.py
```
Access the web interface at `http://localhost:5000`.

## Application Workflow
1. Open the application in your browser.
2. Enter the required details in the provided form.
3. Submit the form to generate predictions.
4. View results, including risk classification and regression metrics. The app validates all inputs and flags invalid values.

## User Inputs
The application form accepts the following:

### Categorical Inputs
- **Channel**: Options include Retail, Broker, Correspondent.
- **First-Time Homebuyer**: Choices are Y or N.
- **Loan Purpose**: P (Purchase) or R (Refinance).
- **Seller Name**: Options include AC, NO, FL, CO.
- **Servicer Name**: Examples include GMACMTGECORP, WELLSFARGOBANKNA.
- **Credit Range**: Very Poor, Poor, Fair, Good, Excellent.
- **LTV Range**: Low, Medium, High LTV.
- **OCLTV Range**: Low, Medium, High LTV.
- **Repayment Range**: E.g., 0-4 years, 4-8 years.

### Numerical Inputs
- **Months Delinquent**: Between 0 and 120.
- **DTI Ratio**: From 0 to 100.
- **Interest Rate**: Up to 20%.
- **Loan Amount (UPB)**: Maximum 1,000,000.
- **Loan Term**: Between 0 and 360 months.
- **Units**: Between 1 and 10.
- **MIP**: Between 0 and 1.
- **Number of Borrowers**: From 1 to 10.

## Debugging and Logs
This app uses Python’s logging library to monitor events and capture errors. Logs are displayed in the console by default.

## Machine Learning Model Details
The model integrates scikit-learn’s tools for preprocessing and prediction:

- **Classification Model**: Predicts prepayment or delinquency risk.
- **Regression Model**: Estimates metrics like repayment amount and timeline.

### Preprocessing Techniques
- Encoding categorical variables using frequency encoding.
- Binning numeric data such as DTI into ranges.
- Creating additional features (e.g., MonthlyPayment, InterestAmount).

### CI/CD Pipeline
#### Workflow Steps:
1. **Build Phase**:
   - Installs dependencies.
   - Builds and pushes a Docker image to DockerHub.
2. **Deployment Phase**:
   - Deploys the updated image to an Azure VM.

#### Secrets Used:
- DockerHub credentials: `DOCKER_USERNAME`, `DOCKER_PASSWORD`.
- Azure VM credentials: `AZURE_VM_IP`, `AZURE_VM_USERNAME`, `AZURE_VM_PRIVATE_KEY`.

![Screenshot 2025-01-01 125217](https://github.com/user-attachments/assets/77290ba5-c7ad-428c-895a-ed3e4d392c39)

##### Then acess the user interface:

![image](https://github.com/user-attachments/assets/e42f1f4c-4577-472f-b736-6d96fbdb98c9)

##### Explore model prediction results:

![image](https://github.com/user-attachments/assets/7d44bd58-84d6-4ade-a4b4-5e8a03d83b1c)


## Contribution Guide
To contribute:
1. Fork the repository.
2. Create a new branch for your feature or fix:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Description of changes"
   ```
4. Push your branch and open a pull request.

## Conclusion 
This project serves as a robust tool for accurately predicting mortgage prepayment and delinquency risks, demonstrating the practical integration of machine learning models into a user-friendly web application for informed decision-making in the mortgage industry.

## Mortgage Backed Securities Prediction
For case study of  mortgage trading, focusing on predicting loan delinquency and prepayment behavior chek the link of repository bellow :

[link](https://github.com/BoukayouaLoubna/MortgageBackedSecuritiesPrediction)


