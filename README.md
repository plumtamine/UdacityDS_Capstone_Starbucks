# UdacityDS_Capstone_Starbucks

It is my capstone project of Udacity Data Science Nano Degree. Following a CRISP-DM process, this analysis supports the research on the responds of customers to the offers sent by Starbucks mobile app. This data set provided by Udacity contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. 

# Prerequisites
Python ver 3.x.

# Business Understanding


# Data Understanding
The data is contained in three files:<br />
portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)<br />
profile.json - demographic data for each customer<br />
transcript.json - records for transactions, offers received, offers viewed, and offers completed<br />
<br />
Here is the schema and explanation of each variable in the files:<br />

portfolio.json<br />
id (string) - offer id<br />
offer_type (string) - type of offer ie BOGO, discount, informational<br />
difficulty (int) - minimum required spend to complete an offer<br />
reward (int) - reward given for completing an offer<br />
duration (int) - time for offer to be open, in days<br />
channels (list of strings)<br />
<br />
profile.json<br />
age (int) - age of the customer<br />
became_member_on (int) - date when customer created an app account<br />
gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)<br />
id (str) - customer id<br />
income (float) - customer's income<br />
<br />
transcript.json<br />
event (str) - record description (ie transaction, offer received, offer viewed, etc.)<br />
person (str) - customer id<br />
time (int) - time in hours since start of test. The data begins at time t=0<br />
value - (dict of strings) - either an offer id or transaction amount depending on the record<br />

# Prepare Data


# Data Modeling
With the cleaned dataset, trained a Random Forest Regression model with price as the target variable. This model is to understand the importance of the features to understand the thrid question. 

# Evaluate the Results


# Featured Deliverables
https://medium.com/@tamine4185/boston-airbnb-listing-pricing-analysis-udacity-project-926121ce3aaf
