# FTW3-Day7: Credit Card Clustering Exercise

## Metadata
Credit card data containing the following information:
- CUST_ID : Identification of Credit Card holder (Categorical) 
- BALANCE : Balance amount left in their account to make purchases 
- BALANCE_FREQUENCY : How frequently the Balance is updated, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated) 
- PURCHASES : Amount of purchases made from account 
- ONEOFF_PURCHASES : Maximum purchase amount done in one-go 
- INSTALLMENTS_PURCHASES : Amount of purchase done in installment 
- CASH_ADVANCE : Cash in advance given by the user 
- PURCHASES_FREQUENCY : How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased) 
- ONEOFFPURCHASESFREQUENCY : How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased) 
- PURCHASESINSTALLMENTSFREQUENCY : How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done) 
- CASHADVANCEFREQUENCY : How frequently the cash in advance being paid 
- CASHADVANCETRX : Number of Transactions made with "Cash in Advanced" 
- PURCHASES_TRX : Numbe of purchase transactions made 
- CREDIT_LIMIT : Limit of Credit Card for user 
- PAYMENTS : Amount of Payment done by user 
- MINIMUM_PAYMENTS : Minimum amount of payments made by user 
- PRCFULLPAYMENT : Percent of full payment paid by user 
- TENURE : Tenure of credit card service for user

## Data Treatment
filled na data with 0

## Clustering Techniques

### KMeans
#### Parameters
- chose 8 clusters using the elbow method 

#### Clusters
##### Cluster 1
-  count = 5239
- low everything.
- low cc users

##### Cluster 2
- count = 453 
- high balance, low purchase, high credit limit, low payment %, low cash advance in high frequency
- cash advance users in low amounts


##### Cluster 3
- count = 1704
- low balance, low purchase in high frequency, high payment %
- uses cc as efficiently, wise spenders

##### Cluster 4
- count = 23
- high balance, high purchases, high credit limit, high payment %,
- **HIGH VALUE**

##### Cluster 5
- count = 114
- low purchases, high cash advance and frequency, high payments, low payment %
- uses creditcard as loan

##### Cluster 6
- count = 55
- low purchases in high frequency, high installment purchases frequency, high minimum payments, low  full payment %
- installment shopper

##### Cluster 7
- count = 337
- high purchases and frequency, low cash advance, high installments, high full payment %
- **high value customer** that uses installments in purchasing

##### Cluster 8
- count = 1025
- high balance, high cash advance, low everything else
- new users that uses CC to cash advance with low payment


### Agglomerative Clustering
- no parameters used
- only two clusters formed

#### Clusters
##### Cluster 1
- count = 5239
- high everything

##### Cluster 2
- count = 453
- low everything
- low economic activities. stagnant economy.

### DB Scan
#### Parameters
- chose epsilon = 2000 at the maximum curvature
- formed 3 clusters

#### Clusters
##### Cluster 1
- count = 945
- high everything except purchase frequency


##### Cluster 2
- count = 7997
- low everything except percentage of full payment

##### Cluster 3
- count = 8
- high purchases and frequency, but zero full payment percentage.

### Gaussian Mixture Models
#### Parameters
- chose 8 clusters using the elbow method (similar with KMeans)

#### Clusters
##### Cluster 1
- count = 1299
- low purchases in high frequency, high installment purchases in high frequency, low minimum payments in high percentage full payment 
- uses cc for installments

##### Cluster 2
- count = 2830
- low everything but high full payment %
- small time cc users with frequent purchases

##### Cluster 3
- count = 941
- high balance freq, low purchasing, high cash advance, high one-off purchase, low payment
- uses cc to loan

##### Cluster 4
- count = 494
- high purchasing, high cash advance, high credit limit, high percentage of payment
- High-value customers

##### Cluster 5
- count = 64
- very high purchases and frequency, high installment purchases, high credit limit, and  high percentage of payment
- high-value customers that don't use cash advance

##### Cluster 6
- count = 1991
- no puchases, low everything but cash advance
- uses cc for loans, 

##### Cluster 7
- count = 1011
- low purchases in high frequency, high cash advance and frequency, high minimum payment,zero percentage of full payment
- uses cc for loans with small frequent purchases

##### Cluster 8
- count = 320
- low purchases in high frequency, high cash advance and frequency, high minimum payment, low percentage of full payment, low tenure
- new cc users with small frequent purchases ang high cash advance usage
