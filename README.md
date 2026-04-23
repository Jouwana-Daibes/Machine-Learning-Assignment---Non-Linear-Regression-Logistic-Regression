# **Non-Linear Regression & Logistic Regression**
## Course Information
- University: Birzeit University
- Faculty: Engineering and Technology
- Department: Computer Engineering
- Course: ENCS5341 – Machine Learning and Data Science
- Assignment: #2

## Project Overview
- This assignment explores two core machine learning concepts:
  -  Part 1: Non-Linear Regression
      - Polynomial Regression with Regularization (Ridge)
      - Radial Basis Function (RBF) Regression
  - Part 2: Logistic Regression
      - Linear Decision Boundary
      - Non-linear Decision Boundary using Polynomial Features

## Objectives
- Understand bias-variance tradeoff
-  Analyze effect of regularization (λ)
-  Explore non-linear feature transformations
-  Evaluate classification models using multiple metrics

## Project Structure
```
├── Assignment2_ML_Presentation.pptx   # Main PowerPoint
├── notebook.ipynb                     # code
├── data/                             # Dataset 
└── README.md
```
### Part 1: Non-Linear Regression
#### Dataset  
Generated 25 data points

#### True function:
     y=sin(5πx)
#### Ridge Regression (Polynomial Features)
    - Degree: 9
    - Tested λ values:
      λ ∈ {0, 1e-12, 1e-10, 1e-8, 0.01}
    - Results (MSE vs True Function)
              λ      Value MSE
              0        0.0335
              1e-12	   0.0302
              1e-10	   0.0267 (Best)
              1e-8	   0.1217
              0.01	   0.4176

          Best λ = 1e-10
          Note: Tiny regularization improves generalization slightly

#### RBF (Radial Basis Function) Regression
  -     RBFs	MSE
        1	    0.4903
        5	    0.3145
        10   	0.0381 (Best)
        50  	Overfitting

#### Key Insight:
- Few RBFs → Underfitting
- Many RBFs → Overfitting
- Moderate number → Best performance

### Part 2: Logistic Regression
#### Dataset
- Customer churn dataset (from Assignment #1)
  Split into:
    - Training: 2500
    - Validation: 500
    - Test: 500
#### Linear Logistic Regression
```
-   Dataset	    Accuracy	Precision	Recall
    Training	  0.9852	  0.9121	  0.7411
    Validation	0.99	    0.9091	  0.8696
    Test	      0.98	    0.8750	  0.6364
```
#### Polynomial Logistic Regression
```
- Degree	     Key Insight
     2	         Slight improvement
     5	         Best balance
     9	         Overfitting
```
#### Model Comparison
```
-  Model	   Observation
   Linear	   Good baseline
   Poly (2)	 Slightly better
   Poly (5)	 Best generalization
   Poly (9)	 Overfits training data
```
Best Model
- Polynomial Logistic Regression (Degree = 5)

 #### ROC Curve
  - AUC = 0.99
    Indicates excellent classification performance
#### Key Insights
##### Regression
  - Small regularization improves performance
  - Model complexity must be controlled
##### Classification
  - Non-linear features improve performance
  - High-degree polynomials can overfit

## Future Work
- Apply cross-validation
- Try other models (SVM, Neural Networks)
- Perform hyperparameter tuning
