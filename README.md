# Unsupervised-ML <br/>
### Unsupervised ML for E-Commerce Dataset and a Flow Chart Table. <br/>
## Dataset Overview:  <br/>
Dataset consisting of five interrelated tables, each containing crucial information about customers, transactions, branches, and merchants. The tables are described as follows:  <br/>
1. Customers Table:  <br/>
○ customer_id: Unique identifier for each customer. <br/>
○ join_date: The date the customer joined. <br/>
○ city_id: The ID representing the customer's city. <br/>
○ gender_id: The ID representing the customer's gender. <br/>
2. Genders Table: <br/>
○ gender_id: Unique identifier for each gender. <br/>
○ gender_name: Name of the gender (e.g., male, female). <br/>
3. Cities Table: <br/>
○ city_id: Unique identifier for each city. <br/>
○ city_name: Name of the city. <br/>
4. Transactions Table: <br/>
○ transaction_id: Unique identifier for each coupon transaction. <br/>
○ customer_id: ID of the customer who performed the transaction. <br/>
○ transaction_date: The date the coupon was claimed. <br/>
○ transaction_status: Status of the coupon (e.g., claimed, burnt). <br/>
○ coupon_name: The name of the coupon. <br/>
○ burn_date: The date the coupon was burnt. <br/>
○ branch_id: ID of the branch where the coupon was burnt. <br/>
5. Branches Table: <br/>
○ branch_id: Unique identifier for each branch. <br/>
○ merchant_id: ID of the merchant who owns the branch. <br/>
6. Merchants Table: <br/>
○ merchant_id: Unique identifier for each merchant. <br/>
○ merchant_name: Name of the merchant. <br/>
## *Used*: <br/>
- python 3.12.4 <br/>
- libraries: pandas,numpy,seaborn,matplotlib. <br/>
- KMeans clustering.
- Data Scaling.
## *In this project*: <br/>
- Data Analysis for a  dataset consisting of five interrelated tables, each containing crucial
information about customers, transactions, branches, and merchants. <br/>
- Dashboard for Stakeholders using PowerBI. <br/>
## *process*: <br/> 
1. Importing important libraries and Loading The Dataset. <br/>
2. Loading the data. <br/>
3. Convirting 'transaction_date' to datetime object. <br/>
4. Calculating recency to know the number of days since the last transaction for each customer. <br/>
5. Calculating Frequency to count the number of transactions per customer. <br/>
6. Aggregateing the number of coupons claimed and burned. <br/>
7. Merging to combine all the data into a single DataFrame. <br/>
8. Handling Missing Values.
9. Features selection,i chose ('recency', 'transaction_count', 'coupons_claimed', 'coupons_burned', 'city_id', 'gender_id'). <br/>
10. Feature scaling to ensure that the features similar scales. <br/>
11. checking the best n_clusters number by using elbow method,the best number of clusters was 3 based on the plot.<br/>
12. Using K_Means clustering. <br/>
13. Printing Inertia and Silhouette score. <br/>
14. Using seaborn and matplot libraries to make a scatterplot matrix to compare the 3 clusters based on: recency,transaction count,coupons claimed,and coupons burned. <br/>
15. Sygment Analysing and Recommendations.<br/>
16. Creating a 3d scatterplot for customer clusters with Plotly and Dimensionality Reduction using PCA.<br/>
## Conclusions:<br/>
## 1. Cluster 0:<br/>
### Recency: <br/>
This cluster consists of customers with higher recency values(they haven’t visited the store in a while).<br/>
### Transaction Count:<br/>
These customers have a low number of transactions.<br/>
### Coupons Claimed:<br/>
Despite the low transaction count, this group has claimed some coupons, though not as actively as other clusters.<br/>
### Coupons Burned: <br/>
The number of burned coupons is low.<br/>
### Behavioral Insight: <br/>
Customers in Cluster 0 are less engaged. They have not visited recently, and their transaction count is low, so they might be at risk of stopping their shopping habits at the store.<br/>
## 2. Cluster 1:<br/>
### Recency: <br/>
These customers have low to moderate recency(they visit the store somewhat frequently).<br/>
### Transaction Count: <br/>
They have higher transaction counts compared to Cluster 0, but not as high as Cluster 2.<br/>
### Coupons Claimed: <br/>
This group claims a good number of coupons.<br/>
### Coupons Burned: <br/>
The number of coupons burned is medium, but lower than Cluster 2.<br/>
### Behavioral Insight: <br/>
Customers in Cluster 1 are moderately engaged. They shop fairly regularly and are somewhat active in using coupons.<br/>
## 3. Cluster 2:<br/>
### Recency: <br/>
This group has the lowest recency values(they visit the store frequently).<br/>
### Transaction Count: <br/>
These customers make the highest number of transactions.<br/>
### Coupons Claimed: <br/>
This group claims the most coupons.<br/>
### Coupons Burned: <br/>
They also have the highest number of burned coupons,so they receive more than they can use or they don't use all the coupons cause they don't need them.<br/>
### Behavioral Insight: <br/>
Cluster 2 customers are the most loyal and active shoppers. They visit the store frequently, make many purchases, and are highly engaged with the store’s coupon offerings. However, the higher number of burned coupons indicates they may be overwhelmed with offers, or the coupons they receive may not always be relevant.<br/>
## Recommendaions and Insights: <br/>
## 1. Cluster 0:<br/>
To re-engage this segment,We should send them attractive and high-value coupons to bring them back to the store (discounts on frequently purchased items,free items for returning to the store) may be a good solution.Offering them personalized, time-limited offers to encourage them to return is a good option too.<br/>
## 2. Cluster 1: <br/>
We should keep these customers loyal with regular coupons but we should focus on increasing their basket size by offering bundled discounts (buy two items and get one free) or coupons for products they haven’t purchased recently to encourage variety in their purchases.<br/>
## 3. Cluster 2: <br/>
To maximize the value from this group, we should offer more personalized and targeted coupons by focusing on optimizing the types of offers they receive to avoid coupon burnout.We can send them coupons based on their past purchase behavior also, we should offer loyalty rewards or exclusive benefits for their continued engagement and loyalty but without overloading them with offers.<br/>
