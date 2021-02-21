# UdacityDS_Capstone_Starbucks

It is my capstone project of Udacity Data Science Nano Degree. Following a CRISP-DM process, this analysis supports the research on the responds of customers to the offers sent by Starbucks mobile app. This data set provided by Udacity contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. 

# Prerequisites
Python ver 3.x.

# Business Understanding


# Data Understanding
The data is contained in three files:
portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)<br />
profile.json - demographic data for each customer<br />
transcript.json - records for transactions, offers received, offers viewed, and offers completed<br />
Here is the schema and explanation of each variable in the files:

portfolio.json

id (string) - offer id
offer_type (string) - type of offer ie BOGO, discount, informational
difficulty (int) - minimum required spend to complete an offer
reward (int) - reward given for completing an offer
duration (int) - time for offer to be open, in days
channels (list of strings)

profile.json

age (int) - age of the customer
became_member_on (int) - date when customer created an app account
gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
id (str) - customer id
income (float) - customer's income

transcript.json

event (str) - record description (ie transaction, offer received, offer viewed, etc.)
person (str) - customer id
time (int) - time in hours since start of test. The data begins at time t=0
value - (dict of strings) - either an offer id or transaction amount depending on the record

# Prepare Data


# Data Modeling
With the cleaned dataset, trained a Random Forest Regression model with price as the target variable. This model is to understand the importance of the features to understand the thrid question. 

# Evaluate the Results


# Featured Deliverables
https://medium.com/@tamine4185/boston-airbnb-listing-pricing-analysis-udacity-project-926121ce3aaf
