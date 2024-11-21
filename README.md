# Credit-Risk-Classification

## Overview of the Analysis
When providing loans, lenders must always mitigate the potential risk of a borrower defaulting on the loan payments in order to avoid financial losses.  It is therefore important that lenders make a proper assessment of a potential borrower so that loans are only provided to those that are most likely to pay back the loans in a timely matter.  The purpose of this analysis is to create a machine learning model for a peer-to-peer lending company that could accurately assess data on a potential borrower and identify their creditworthiness.

The data used to train and test this model is derived from a data file of historical lending activity (77,536 rows) from a peer-to-peer lending services company that contains the following fields:
* Loan size/amount
* Loan interest rate
* Borrower's income
* Borrower's debt to income ratio
* Number of borrower's current credit accounts
* Number of derogatory marks on borrower's record
* Borrower's total debt
* Loan status where 0 = healthy loan and 1 = loan with high risk of defaulting

Based on this available data, it was determined that 'loan status' would be the metric to gauge a borrower's creditworthiness and serve as the dependent variable that the model would predict based upon the other fields or features (independent variables).

To create the model, Python was used as the base programming language combined with the pandas and sklearn libraries.  After reading the raw data file into a Pandas DataFrame, the data was used to create two sets: a 'y-variable' or 'labels' set ('loan status') and an 'x-variable' or 'features' set (all other independent variables).  Once the two sets were created, the data was then randomly split into training and test datasets (75% of the data for training the model and the remaining 25% for model testing).

The training dataset was then used to fit, or train, our chosen regression model.  Since the goal of the model is to classify data into a specific category (healthy vs high-risk) rather than estimating a continuous variable, a logistic regression model made the most sense to use.  The trained logistic regression model was then evaluated by having it generate 'loan status' predictions based on the test dataset and then comparing the predictions to the actual 'loan status' values.

## Results

The resulting model produced the following scores: 

* Accuracy: ~99%
    * The model correctly predicted the loan status of approximately 99% of the loans

* Precision: Healthy Loans: ~100%, High-Risk Loans: ~87%
    * Out of all the loans that the model predicted as healthy, approximately 100% of them actually were.
    * Out of all the loans that the model predicted as high-risk, approximately 87% of them actually were.

* Recall: Healthy Loans: ~100%, High Risk Loans: ~95%
    * Out of all the loans that were actually healthy, the model correctly predicted approximately 100% of them as healthy.
    * Out of all the loans that were actually high-risk, the model correctly predicted approximately 95% of them as high risk.


## Summary
Overall, when classifying a loan for a borrower as healthy or at high risk of default, the trained logistic model yielded a high overall accuracy rate of ~99%.  The model showed a very strong ability to predict healthy loans with low risk of default, demonstrating both near perfect precision (~100% of the loans it classified as healthy actually were) and recall (~100% of the loans that were actually healthy were predicted as such by the model).  The model also performed reasonably well when predicting when loans had a high risk of default, with a decent level of precision (~87% of the loans that were classified as high risk actually were) and strong recall (~95% of the loans that were actually high risk were predicted as such by the model).

These performance scores support a recomendation to integrate the model into the borrower assessment process.  However, given that the model is, like many models, not 100% accurate, it should not be the sole determinant of a borrower's crediworthiness but rather be used as a supplementary tool.  Given that the model's performance is better when determining healthy loans with lower risk of default, it may be best to use it to streamline or fast-track the process for potential borrowers that the model predicts would yield a healthy loan repayment.  As for loans for borrowers that the model deems high risk, it maybe be best to add additional forms of assessment on top of the model's predictions, since the precision results indicate that model has a chance of incorrectly classifying healthy loan borrowers as high risk.



### Dependencies
* Python (w/ jupyter notebook) and the following libraries/framworks
    * pandas
    * sklearn
    * pathlib
    * numpy
* The following .csv files are required (stored in the 'Resources' folder):
    * lending_data.csv

### Installing & Execution
The repository files can be downloaded to open and execute the 'credit_risk_classification.ipynb' file.  Note that since 'credit_risk_classification.ipynb' contains relative file paths, it is important to maintain the file directory structure in order for it to execute properly.

## Authors

Daniel Pineda

## Acknowledgments
Credit-Risk-Classification was created as an assignment for the University of California, Irvine Data Analytics Bootcamp - June 2024 Cohort under the instruction and guidance of Melissa Engle (Instructor) and Mitchell Stone (TA).
The practical exercises and coding examples demonstrated through the bootcamp helped inform and inspire the code for this project.