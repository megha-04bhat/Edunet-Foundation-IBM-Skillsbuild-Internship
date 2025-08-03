# Intelligent Classification of Rural Infrastructure Projects

This project aims to automate the classification of rural infrastructure projects under the Pradhan Mantri Gram Sadak Yojana (PMGSY) into their respective schemes (PMGSY-I, PMGSY-II, RCPLWEA, etc.) using machine learning techniques powered by IBM Watson Studio AutoAI.

## 📌 Problem Statement

Manual classification of thousands of infrastructure projects is inefficient and prone to error. Accurate classification is essential for effective policy-making, monitoring, and transparent budgeting. This project uses AI to classify projects based on physical and financial features such as project cost, length, terrain, and funding year.

## 💡 Proposed Solution

A machine learning pipeline was built using IBM Watson AutoAI to:
- Ingest and preprocess project data
- Automatically select and train the best ML algorithm
- Deploy the model to IBM Watson Machine Learning (WML)
- Use the model via an API endpoint

## 🧠 Technologies Used

- IBM Watson Studio 
- IBM AutoAI
- IBM Cloud Object Storage
- IBM Watson Machine Learning (WML)
- Python (within AutoAI-generated notebooks)

## ⚙️ Features and Workflow

1. **Data Upload**: AI Kosh dataset uploaded to IBM Cloud Object Storage.
2. **AutoAI Training**:
   - Features: `STATE_NAME`, `DISTRICT_NAME`, `NO_OF_ROAD_WORK_SANCTIONED`, `LENGTH_OF_ROAD_WORK_SANCTIONED`, `NO_OF_BRIDGES_SANCTIONED`, `COST_OF_WORKS_SANCTIONED`, `NO_OF_ROAD_WORKS_COMPLETED`,`LENGTH_OF_ROAD_WORK_COMPLETED`, `NO_OF_BRIDGES_COMPLETED`,`EXPENDITURE_OCCURED`
   - Target: `PMGSY_SCHEME`
   - Algorithm chosen: **Batch Tree Ensemble Classifier**
3. **Model Deployment**:
   - AutoAI deployed the best model to WML.
   - API endpoint generated for external integration.
4. **Prediction**:
   - Input new project details.
   - Receive predicted PMGSY scheme classification from the deployed model.

