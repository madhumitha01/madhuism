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
image: assets/images/insta1.jpg
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

![walking]({{ site.baseurl }}/assets/images/orders.jpg)

## Data Exploration

### Let's validate the claim that 4 to 100 orders of a customer are given

There are two types of code elements which can be inserted in Markdown, the first is inline, and the other is block. Inline code is formatted by wrapping any word or words in back-ticks, `like this`. Larger snippets of code can be displayed across multiple lines using triple back ticks:

```
.my-link {
    text-decoration: underline;
}
```

If you want to get really fancy, you can even add syntax highlighting using Rouge.

![walking]({{ site.baseurl }}/assets/images/orders.jpg)

## Reference lists

The quick brown jumped over the lazy.

Another way to insert links in markdown is using reference lists. You might want to use this style of linking to cite reference material in a Wikipedia-style. All of the links are listed at the end of the document, so you can maintain full separation between content and its source or reference.

## Full HTML

Perhaps the best part of Markdown is that you're never limited to just Markdown. You can write HTML directly in the Markdown editor and it will just work as HTML usually does. No limits! Here's a standard YouTube embed code as an example:

<p><iframe style="width:100%;" height="315" src="https://www.youtube.com/embed/Cniqsc9QfDo?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>
