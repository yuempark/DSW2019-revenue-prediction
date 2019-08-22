# Google Analytics Customer Revenue Prediction

Group project for the 2019 Data Science Workshop hosted by the Graduate Data Science Organization at the University of California, Berkeley.

The project is the Google Analytics Customer Revenue Prediction competition on Kaggle: https://www.kaggle.com/c/ga-customer-revenue-prediction

## Group Members

* Andy Vargas (mentor)
* Yuem Park
* Marvin Pohl
* Michael Yeh

Note: The duration of the workshop was short and taken in conjunction with ongoing graduate research. Therefore, the following code may not be documented/written in a way that is optimal... if you have any questions regarding this project, please do not hesitate to contact any of the group members listed above.

## Project Description

For many businesses, only a small fraction of customers produce the majority of the revenue. Therefore, identifying these potentially revenue-generating customers is critical for developing effective marketing strategies. Our project used visitor data from the online Google Merchandise Store to predict future customer revenue. Given that the vast majority of visitors never purchase anything in the future, we used a two-model approach: first, a logistic regression was used to quantify the probability that a given customer would make a purchase in the future (which we refer to as `probability` in the files described below), and second, a random forest was used to estimate the amount of money that a given customer was going to spend under the assumption that they did make a purchase in the future (which we refer to as `regression` in the files described below). By multiplying these two values together, we were able to estimate the expected value of any given customer with an accuracy that approximates the best-performing models to date.

## Repository Organization

* `./data/`
    * this is a directory added to the `.gitignore`, given that the files insde are too large to upload to GitHub in the traditional way.
    * the directory should contain the following files, all downloaded directly from the Kaggle competition website:
        * `sample_submission_v2.csv`
        * `test_v2.csv`
        * `train_v2.csv`
    * the directory also contains other large data files that are generated in the notebooks described below

* `probability.ipynb`
    * contains the code that performs the data exploration and feature engineering for the logistic regression probability model

* `regression-model-feature-engineering.ipynb`
    * contains the code that performs the data exploration and feature engineering for the regression model

* `exploratory-regression-models.ipynb`
    * contains the code that tests various machine learning algorithms for the regression model
    * `train_df_X.csv`
        * feature engineered training datasets for input into the regression machine learning algorithms
    * `test_df.csv`
        * feature engineered testing dataset for input into the regression machine learning algorithm

* `refined-regression-model.ipynb`
    * contains the code that applies the best performing machine learning algorithm (random forest regressor)
    * `RFR_prediction_train.csv`
        * random forest regressor predictions for the training dataset
    * `RFR_prediction_test.csv`
        * random forest regressor predictions for the testing/evaluation dataset

* `DSW-presentation.pdf`
    * brief slide deck used to present our project
    
* `submission.csv`
    * final output of the model on the test data that was submitted to Kaggle
