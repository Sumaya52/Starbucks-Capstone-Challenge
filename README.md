# Starbucks-Capstone-Challenge
This project is the capstone project of the Udacity’s Data Scientist Nanodegree. The data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

## Problem Statement
This project aims to combine transaction, demographic and offer data to determine which demographic groups respond best to which offer type.
In addition, we define a methodology to determine whether an offer on the Starbucks app is a successful offer or not and develop ML classifers to solve this problem.

## Datasets Description
The data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

**portfolio.json**
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

**profile.json**
* age (int) - age of the customer 
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

**transcript.json**
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## Libraries
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## Results
1. The master dataset has 56759 entries of unique person_id and offer_id combinations.
2. There are 28820 rows of unsuccessful offer and 27939 rows of successful offers. Luckily, this create a balanced dataset.
3. The most successful offer is offer 8 where the least successful offer is offer 5.
4. The offer type doesn’t seem to play a huge rule in offer success.
5. Females tend to have more successful offers than men.
6. Customers who became members at the year 2018 have the least successful offer rate.
7. The higher the income, the higher the success offer rate.
8. Age doesn’t seem to play a huge rule in offer success.
9. Random Forest classifier has outperformed the other three classifiers (KNN, LR and GNB) with an accuracy of 93%.

## Medium Blog Post
The project steps and results have been communicated through medium blog post found in [this link](https://medium.com/@sumaya52.ksa/starbucks-capstone-challenge-dca3b1172072).
