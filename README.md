#### Analysis / ML Report in Korean 🇰🇷 
###### https://github.com/SuhyunL/Jewerly-Ecommerce-Store-Analysis-ML/blob/main/%5BPDF%2C%20KOR%5DJewelry%20Project_ppt.pdf


#### Wanna read some articles about the insights that I got from this analysis?
##### - Visit https://suhyun-lee.medium.com/trend-talk-with-data-46ee0eb82a8e<br/> - Or https://suhyun-lee.medium.com/how-did-covid-19-impact-on-fashion-industry-e241975183a0


# **Introduction**

E-commerce market is one of the fastest growing industry. This data contains data from 2018, when fashion e-commerce begain in earnest worldwide to 2020, when e-commerce market showed remarkable growth through Covid-19. I would like to view this data in 3 big perspectives of sales - Brand, Product, and Sales itself.


# **Analysis**

## **🔹 Sales Analysis**
### 1. Sales by time
**Do the sales depend by time? (ex. day, month, or seasons?)**
  - Sales by Month
  ![image](https://user-images.githubusercontent.com/75061420/126739845-1b663478-8aa1-4111-96ee-a80b3fea4f93.png)
  Before Covid-19, Sales increased on holiday seasons, especially at the end of the year.
 
 
![image](https://user-images.githubusercontent.com/75061420/126739787-9e297820-e731-46d5-b251-80662d974c88.png)
  But recently, after the Covid-19, the virus impacted the sales more than the month. If there are higher cases, sales gets lower immediately. When there are lower cases, sales increase. Higher cases made people to stay inside, which reduced the spendings for apparels to go outside.
  
  - Sales by time
  ![image](https://user-images.githubusercontent.com/75061420/126740003-47db353d-77a0-442e-8626-4658a1ac60d1.png)
  
  Turned out that 10AM-1PM is the golden hour for daily sales.
  
  - Sales by day
  ![image](https://user-images.githubusercontent.com/75061420/126740025-60465941-2a60-4c1a-a30c-8a349ebab6d4.png)
  Sales peaked on Thursday. Sales decreased during the weekend, when people go outside and oine sales hit the apex.

### 2. Sales by Frequency of Repurchase
**How high is the repurchase rate?**

![image](https://user-images.githubusercontent.com/75061420/126740142-85b404cc-f023-4798-b613-93d6fc79fb9a.png)

The repurchase rate is 17%, which is comparatively very high. There is a high frequency until the second repurchase, but the frequency decreases significantly from the number of repurchases. Meanwhile, the most repurchases are 231.

**Are there any brands that are particularly repurchased?**
![image](https://user-images.githubusercontent.com/75061420/126740325-18b2617b-b131-4af9-bf6f-af241944c6d4.png)

Brand 1, one of the highest-sales brand shows 53% of remarkably high repurchase rate, which means repurchase accounts for more than half of their entire purchase.


## **🔹 Brand Analysis**
**What is an overall landscape of brands?**
![image](https://user-images.githubusercontent.com/75061420/126740389-734b20e4-d6ee-415e-a4d7-9bc866e54521.png)

Brand #0, #1 account for the most of sales. Brand #6 is very rarely purchased.

**How is the game changing by each brand? Which brand has the biggest potential?**
![image](https://user-images.githubusercontent.com/75061420/126740348-fd984090-73ab-41c9-a6b2-821f24e7af1a.png)
Brand #0 was a conventional winner.
Meanwhile, Brand #1 is showing a rapid growth, fiercely chasing it's competitor brand #0, and finally turned the table.
Brand #1 seems like having the biggest potential.


## **🔹 Trend Analysis**
### 1. Trend from a perspective of product
**- How long each trendy product lasts?**
![image](https://user-images.githubusercontent.com/75061420/126740691-9c2cdc97-5c27-4ca4-ab8a-98003ecf8c56.png)
It greatly differs by products. Some trends last, some trends vanish.

**- What does each trend cycle looks like? Are they mostly look alike?**
![image](https://user-images.githubusercontent.com/75061420/126741219-e65001b2-5529-4985-9564-0258ac75f8f4.png)

In most cases, the left tail is elongated, and they suddenly decrease after reaching the apex. Outside of their steep growth, it looks similar to PLC. The steeper growth can be reasoned as the bigger boost in the fashion industry when certain products become trendy.

**- Does trend leader exist?**

> Yes, they exist. There was even a customer that 70% of the product that he/she bought became trendy afterward. For example, Customer #757 was an early buyer of 61 out of 86 trending products. 70% of the products this customer bought became trendy. #41, #49, and #59 were also the trend leaders as being early buyers from the majority of trending products.

**- What about Trend Followers?**
There were trend followers, also. There were about 10,000 people, which is nearly 25% of all customers. Customers #805, #77b4, #437 bought all of the trending products and even repurchased some of them. More than 30 people bought half of all the trending products.

**- What seems like an upcoming trend?**
![image](https://user-images.githubusercontent.com/75061420/126742356-525cd77f-bc61-4743-bf30-1cb914f62ec0.png)
According to the trend leaders' recent purchases, Gold ring with a diamond seems like a trend.

# **Machine Learning Model**
## **🔹 Insights**
### 1. Sales Analysis
Covid directly impacted on Sales. Meanwhile, out repurchase rate is 17%, which is very high compared to other jewerly shops.
### 2. Brand Analysis
Brand #1 seems like having the biggest potential.
Brand #1 is showing a rapid growth, fiercely chasing it's competitor brand #0, and finally turned the table.
### 3. Trend Analysis
Trend and Trend leader existed. Most of trends were drawing PLC line and there were some trend leaders who have shown 70% accuracy. According to the trend leaders' recent purchases, Gold ring with a diamond seems like a trend.

## **🔹 Modeling**
To increase sales, we need to highlight our strength- high repurchase rate. The core of high repurchase rate is reasonable price and good products. The price turned out to be seasonable, but the problem was in the products. There are too many products that are purchased only once (low sales). The trend exists, but the trendy products are hardly noticeable as there are too much products that are behind the trend, interferes the exposure.

Therefore, we need a machile learning model which can predict future sales and leave sellable products so we can improve product pools, which will eventually raise repurchase rate.

### Model 1. Binary Classification Model
- Predicts whether a product will be sold next quarter or not.
- Feature selection: Didn't selected the feature- used whole feature but noised each of it so the model choose actual impact features by itself.
- Model: XGB Boost (showed best performance in multiple experiments/ n_estimators = 400, scale_pos_weight = ratio, max_depth = 9, subsample = 0.9)
- Performance: Detected 80% of non-sold item & 93% of sold items.

### Model 2. Rigression Model
- Predicts how much it would be sold next quarter.
- Feature selection: Used most of the features and left it to the model itself, but deleted 'quantity-per quarter' feature as it can cause data leakage.
- Model: LGBMRegressor(num_boost_round = 1000, learning_rate = 0.1, num_iterations = 90, max_depth = 8, metric = 'l1', max_bin = 446, min_data = 42)
- Performance: R2 0.82/ MAE 983/ MSE 3187948/ RMSE 1785


# **Expected Effect**
- Improve overall product composition and save cost by leaving products worth selling.
- Able to put more focus on potential items by predicting next quarter sales by products.
- Eventually enhance repurchase rate and overcome stagnant sales.
