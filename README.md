# Customer Support Ticket Classification & Priority Prediction

## Overview

This project presents a Natural Language Processing (NLP) system that automatically classifies customer support tickets and assigns priority levels.
The goal is to help support teams organize incoming requests, identify urgent issues faster, and improve response efficiency.

## Key Features

- Text preprocessing (cleaning and normalization)  
- Feature extraction using TF-IDF  
- Ticket category classification (e.g., Account, Security, Billing)  
- Priority prediction (High / Medium / Low)  
- Handling class imbalance  
- Model evaluation using precision, recall, and F1-score  
- Data visualization for insights  

## Project Workflow

Raw Data → Text Preprocessing → Feature Engineering → TF-IDF → Model Training → Prediction → Evaluation

## Dataset Description

The dataset consists of real-world customer support tickets with the following fields:

- **subject** → short summary of the issue  
- **body** → detailed ticket message  
- **tag_1** → ticket category (target for classification)  
- **priority** → urgency level (target for prediction)  
- **language** → ticket language  

### Preprocessing Steps

- Filtered English-language tickets  
- Removed missing values  
- Combined **subject + body** for richer text representation  
- Cleaned text (lowercasing, removing special characters)  
- Removed rare categories (less than 20 samples) to address class imbalance  

## Model Approach

### Feature Engineering

Text data is transformed using **TF-IDF vectorization**, capturing the importance of words across the dataset.

### Models Used

Two supervised machine learning models were built using **Logistic Regression**:

- **Category Model**
  - Input: Ticket text  
  - Output: Ticket category (tag_1)

- **Priority Model**
  - Input: Ticket text  
  - Output: Priority level (high, medium, low)

Updated version:
- Replaced Naive Bayes with Logistic Regression
- Applied class balancing to improve performance

### Why Logistic Regression?

- Performs well on high-dimensional text data  
- Works effectively with TF-IDF features  
- Supports class weighting to reduce bias toward dominant classes  

## Handling Class Imbalance

The dataset contained many low-frequency categories, which affected model performance.

To address this:

- Categories with fewer than 20 samples were removed  
- Class weighting (class_weight='balanced') was applied  

These steps improved model generalization and reduced bias toward dominant categories.

## Results & Evaluation

Models were evaluated using:
- Accuracy  
- Precision  
- Recall  
- F1-score 

### Key Observations

- Improved performance compared to the initial Naive Bayes baseline  
- Strong results on frequently occurring categories  
- Better handling of minority classes after filtering  
- Reduced occurrence of zero-score predictions  

## Visualizations

### Top Ticket Categories  
<img width="655" height="599" alt="image" src="https://github.com/user-attachments/assets/0a0e5547-eb18-4f93-9d9e-a94b3680297d" />
 
### Priority Distribution  
<img width="630" height="573" alt="image" src="https://github.com/user-attachments/assets/85dc0697-5f43-4dbd-9cae-a3bef44bccd1" />

## Example Prediction

**Input:**  
My account is locked and I need urgent help  

**Output:**  
- Category: Account  
- Priority: High  

## Insights

- Customer support data is highly imbalanced  
- A small number of categories dominate the dataset  
- Combining subject and body improves classification performance  
- Model performance is strongly influenced by data distribution  

## Future Improvements

- Experiment with advanced NLP models (e.g., Transformers, BERT)  
- Apply oversampling techniques for minority classes  
- Perform hyperparameter tuning  
- Deploy as a web application or API  
- Build a real-time ticket processing system  

## Quick Start

1. Clone the repository  
git clone https://github.com/MahleMeyi/FUTURE_ML_02.git
cd FUTURE_ML_02
2. Install dependencies
Make sure you have Python installed (Python 3.8+ recommended), then run:
pip install pandas numpy scikit-learn matplotlib
3. Run the notebook in Jupyter or Google Colab(Recommended)
Open the .ipynb file in Google Colab
Upload the dataset (aa_dataset_tickets_multi_lang.csv)
Run all cells

## Conclusion

This project demonstrates how NLP and machine learning can automate customer support workflows.
By classifying tickets and predicting priority levels, organizations can streamline operations, reduce response time, and improve customer experience.
