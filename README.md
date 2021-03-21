# UdacityDS_Capstone_Starbucks

Project Overview <br />

It is my capstone project of Udacity Data Science Nano Degree. This analysis supports the research on improving the responses of customers to the offers sent by the Starbucks mobile app. This data set provided by Udacity contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offers during certain weeks.

# Prerequisites
Python ver 3.x.

# Problem Statement
The goal is to better target the customers with marketing campaigns (whether to send a customer a discount, BOGO, or an advertisement). First, this analysis will share some insights about the features of the customers in EDA phase. Then this analysis will use K-means clustering to segment the customers. 

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
# EDA
1. There are 38% more male customers than female customers.<br />
2. Male customers are right-skewed while female customers are more evenly distributed by income. The average income is 65405.<br />
3. Average male customers are younger than average female customers. The total customer portfolio is 62..5 years old.<br />
4. Most customers became members from 2016 to 2018 with much more new female customers.<br />
5. While both BOGO and discount offers are almost evenly distributed to customers in the sense of total amount and 10% fewer customers viewed discount offers than BOGO offers, 11% more discount offers are completed.

# Data Modeling
With the cleaned dataset, trained a K-means cluster model to segment the customers. 
# Metrics
Metrics in Attributes: <br />
***View Through Rate:*** offer_viewed / offer_received and <br /> 
***Conversion Rate:*** offer_completed / offer_viewed  <br />
calculated based on transcript dataset <br />

Metrics in model evaluation: With K-means cluster model in this analysis, I am using ***Percentage of Variance Explained (PVE)*** to descide how many clusters will be the best to segment the customers with the data sample. <br />

# Evaluate the Model Results
Interpreting the 3 clusters from the K-means model:<br />
Cluster_1 Highly incentivized group: This group of customers have the highest income at around 69K with a balanced mix of gender. Most of them become members in 2016 and 2017. With an average CVR at 91% and VTR at 82%, this group of customers are highly responsive to the offers but not so much with advertisements. 
<br />
Cluster_2 Advertisement attracted group: This group of customers is more attracted to view the offers, especially like to open up the advertisement ones. This group of customers are mostly male and are new customers that became members in 2017 and 2018. They also tend to spend more. Combined with a low CVR, this group of customers is not prone to discount and BOGO offers and tends to consume without marketing offers. So this group of customers is more suited to send advertisements to. 
<br />
Cluster_3 Potential customers group: This group of customers doesn't like to provide full personal profile information so didn't fill in gender, income, or age when signing up. However, they are also more likely to be incentivized by the discount and BOGO offers. This is a group of customers that are more cautious when making consumptions and have the potential to be attracted by marketing campaigns. This group is a great target segment to expand marketing campaign influence. 
<br />


# Reflection
Before applying the clustering model, my assumption is there will be 3 groups, one group that is prone to BOGO offer, one to Discount offers, and the rest are indifferent to promotion offers or are more likely to attracted by advertisements. While the result is still 3 segments, what these 3 segments represent is completely different from what I assumed. The result makes more sense from the perspective and persona of customers rather than the perspective of the company. This experience was very interesting as it provided an opportunity for me to look at the business question from the customers' perspective enlightened by data.<br />
As far as the whole analysis experience, I went back and forth with the data cleaning and data preparation steps, which are phases that I spent the most time on. I first used the transcript data to run the model because I'd like to understand how each transaction worked out. Then changed it back to customer profile data, which makes more sense as to understand customer segmentation. <br />

# Possible improvements
My first impression of selecting an algorithm for this analysis is clustering so I continue the route. After this clustering model, I feel it can be used to label the provided dataset and then be applied to supervised modeling to predict new customers' reactions given different persona and offers. 
# Next steps 
The next step is to validate the segments in real-life settings. so A/B testing should be applied to see how the marketing campaigns perform within the 3 segments divided by the model above.

# Featured Deliverables
https://medium.com/@tamine4185/starbucks-customer-clustering-analysis-udacity-project-ddea21250720
