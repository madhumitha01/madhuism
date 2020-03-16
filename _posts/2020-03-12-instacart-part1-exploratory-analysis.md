---
layout: post
title: "Instacart Market Basket Analysis Part 1: Exploratory Data Analysis"
author: sal
categories:
  [
    Instacart,
    Data Analysis,
    Data Science,
    Exploratory Analysis,
    Market Basket Analysis,
  ]
image: assets/images/insta1.jpeg
beforetoc: "Instacart market basket analysis was a Kaggle competition that was opened early 2016 and was conducted by Instacart."
toc: true
---

## What is Instacart?

Instacart is a grocery ordering and delivery app that aims to make it easy to fill refrigerator and pantry with personal favorites and staples when needed. After selecting products through the Instacart app, personal shoppers review the order and do the in-store shopping and delivery for customers.

Instacart uses transaction data to develop models that predict which products a user will buy again, try for the first time, or add to their cart next during a session. The objective for this competition was to use the data on customer orders over time to predict which products will be in a user's next order.

## About the Dataset

The dataset is anonymized and contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. For each user, the dataset provides between 4 and 100 of their orders, with the sequence of products purchased in each order.

Instacart has also taken great care to protect the privacy of their users and retail partners and to ensure that the data is entirely anonymous:

<ul>
<li>
The only information provided about users is their sequence of orders and the products in those orders.</li>
<li>
All of the IDs in the dataset are entirely randomized, and cannot be linked back to any other ID.</li>
<li>
Only products that are bought by multiple people at multiple retailers are included, and no retailer ID is provided.</li>
</ul>

This dataset includes orders from many different retailers and is a heavily biased subset of Instacart's production data, and so is not a representative sample of their products, users or their purchasing behavior.

![dataset]({{ site.baseurl }}/assets/images/orders.png)

## Data Exploration

<i> Code for all the graphs represented below are present in this <a href="https://github.com/madhumitha01/Instacart-Market-Basket-Analysis/blob/master/Instacart-%20Exploratory%20Analysis.ipynb">GitHub repository.</a></i>

### Validating 4-100 orders of customer

**_Let's validate the claim that 4 to 100 orders of a customer are given_**
![Analysis1]({{ site.baseurl }}/assets/images/exp1.png)

As stated in the problem description, there are <b>no orders less than 4 and is max capped at 100</b>.

### Order vs Week/Days

**_Let's see how ordering habit changes w.r.t day of week & hour of day_**

![Analysis2]({{ site.baseurl }}/assets/images/exp2.png) ![Analysis3]({{ site.baseurl }}/assets/images/exp3.png)

- <b>Frequency of order by day of week</b>- 0 and 1 represents Saturday and Sunday when the orders are high and low during Wednesday
- <b>Frequency of order by hour of day</b>- Majority of the purchases are made during day time, i.e. between 10 am to 4 pm.

### Day of week vs Hour of day

**_Let's combine the day of week & hour of day to see the distribution_**

![Analysis4]({{ site.baseurl }}/assets/images/exp4.png)

From the graph, we can see that **Saturday evenings and Sunday mornings** are the prime time for customers to make orders.

### Interval between each order

**_Let's see the time interval between previous & present orders_**

![Analysis5]({{ site.baseurl }}/assets/images/exp5.png)

- Graph states that customers order **once in every week** (peak at 7 days) or **once in a month** (peak at 30 days).
- Also, we can see that there are smaller peaks at 14, 21 and 28 days (weekly intervals).

### Each order contained how many products?

**_Let's see no. of products bought in each order & most ordered products_**

![Analysis6]({{ site.baseurl }}/assets/images/exp6.png) ![Analysis7]({{ site.baseurl }}/assets/images/exp7.png)

- We can observe from the plot that people usually order **around 5 products**.
- In particular, the **top 5 most ordered products are** Banana (491,291), Bag of Organic Banana (394,930), Organic Strawberries (275,577), Organic Baby Spinach (251,705), and Organic Hats Avocado (220,877).

### Important Aisles and Departments

**_Now let's look at the important aisles and department distribution_**

![Analysis8]({{ site.baseurl }}/assets/images/exp8.png) ![Analysis9]({{ site.baseurl }}/assets/images/exp9.png)

- **Top aisles** are fresh fruits, fresh vegetables, packaged vegetables and fruit, followed by yogurt and packaged cheese.
- The **top department** is produce, followed by dairy eggs and snacks.

### Reorder Ratio

**_Now let's look at reorder ratio of each Department_**

![Analysis10]({{ site.baseurl }}/assets/images/exp10.png)

From the point plot, we can find that Personal care has lowest reorder ratio and **dairy eggs has highest reorder ratio**.

### Cart order vs Reorder ratio

**_Let's look at the cart order vs the reorder ratio_**

![Analysis11]({{ site.baseurl }}/assets/images/exp11.png)

- We can see that the **products that are added to the cart initially are the ones that are likely to be reordered again** compared to the ones added later.
- This makes sense to as we tend to first order all the products we used to buy frequently and then look out for new products available.

## Conclusion

<ol>
<li>The dataset is quite big and has many variables that we can analyze. We can further look at association rules in detail between products, investigate consumer reordering patterns in terms of days and hours, reorder ratio vs the hour of the order and so on…</li>
<li>Some of the business related problems that might have an impact on the revenue are:
<ul>
<li>
Frequency of customer orders is low ranging from 4–12. <b>What actions can a business take in order the improve the frequency of customer orders?</b></li>
<li>Majority of the customers plan their purchases on weekly and monthly cycles. <b>What actions can a business take to improve the purchases for any day of the week and month?</b></li>
<li>Besides banana, top items are sold mostly on Monday and Tuesday. <b>Can this be related to an item inventory issue from the retailers?</b></li>
<li><b>Besides the general consumer and market needs, are there any reasons why certain department sales are lower than the others?</b></li>
</ul>
</li>
</ol>

- _If you are interested in reproducing this result yourself, you can download the dataset from the <a href="https://medium.com/r/?url=https%3A%2F%2Fwww.instacart.com%2Fdatasets%2Fgrocery-shopping-2017">Instacart website</a> and view my notebook on <a href="https://github.com/madhumitha01/Instacart-Market-Basket-Analysis/blob/master/Instacart-%20Exploratory%20Analysis.ipynb">GitHub.</a>_

- _In the next part of this blog post series, I will do Customer Segmentation, which can help Instacart find the behavioral pattern between their customers and deliver more personalized recommendations based on their needs._
