# Customer Support Ticket Classification & Priority Prediction

## Overview
This project implements a Natural Language Processing (NLP) system that automatically classifies customer support tickets and assigns priority levels.  
The goal is to help support teams organize incoming requests and respond more efficiently.

## What This Project Does
- Cleans and preprocesses raw support ticket text  
- Converts text into numerical features using TF-IDF  
- Classifies tickets into categories (e.g., Account, Security, Billing)  
- Predicts priority levels (High, Medium, Low)  
- Evaluates model performance using standard metrics  
- Visualizes ticket category and priority distributions  

##  Project Workflow
Raw Ticket Data -> Text Cleaning -> TF-IDF Vectorization -> Model Training -> Prediction -> Evaluation

## Tools & Technologies
- Python  
- Pandas  
- Scikit-learn  
- Matplotlib  
- Google Colab

## Model Approach
The dataset was filtered to include only English-language tickets and cleaned to remove noise such as punctuation and special characters.  
Text data was transformed using TF-IDF vectorization, allowing machine learning models to understand word importance.  
Two classification models were built using Multinomial Naive Bayes:
- **Category Model** -> predicts the type of support ticket  
- **Priority Model** -> predicts the urgency level  

## Results
- The models achieved reasonable accuracy in both classification tasks  
- Performance is stronger on frequently occurring categories  
- Some misclassifications occur due to similar wording between tickets

## Visualizations

### Top Ticket Categories
<img width="664" height="607" alt="image" src="https://github.com/user-attachments/assets/cd9adf22-31a3-45f9-a237-fe20531080ea" />

### Priority Distribution
<img width="637" height="561" alt="image" src="https://github.com/user-attachments/assets/4ec6bded-4180-4a2b-a895-c1b9d82b9628" />

## Example Prediction

**Input:**
My account is locked and I need urgent help

**Output:**
Category: Account
Priority: High

## Insights
- A small number of categories dominate the dataset  
- Priority prediction helps identify urgent issues quickly  
- Text similarity between categories can affect model accuracy  

## Future Improvements
- Experiment with advanced NLP models (e.g., LSTM, Transformers)  
- Perform hyperparameter tuning  
- Handle class imbalance for better accuracy  
- Deploy as a web application or API  

## Conclusion
This project demonstrates how NLP and machine learning can automate customer support workflows.  
By classifying tickets and assigning priority levels, organizations can improve response times and the overall efficiency.
