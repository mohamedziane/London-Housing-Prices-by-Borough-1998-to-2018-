# Investigating London boroughs Housing Prices.
# Which boroughs of London have seen the greatest increase in housing prices, on average, over the last two decades?


<p align="center">
  <img width="600" height="500" src="https://www.local-government.org.uk/images/Greater_London-Boroughs.png">
</p>

## 1. Introduction

In this notebook, here’s the mystery we’re going to solve: ***which boroughs of London have seen the greatest increase in housing prices, on average, over the last two decades?***


A borough is just a fancy word for district. You may be familiar with the five boroughs of New York…etc, there are 32 boroughs within Greater London [(here's some further information)](https://en.wikipedia.org/wiki/London_boroughs). Some of them are more desirable areas to live in, and the data will reflect that with a greater rise in housing prices.

**The Data Science Pipeline**

Data Science is magical. In this case study, we'll get to apply some complex machine learning algorithms. But as  [David Spiegelhalter](https://www.youtube.com/watch?v=oUs1uvsz0Ok) reminds us, there is no substitute for simply **taking a really, really good look at the data.** Sometimes, this is all we need to answer our question.

We will adhere to the four stages of a typical Data Science Pipeline:

- Sourcing and loading 
- Cleaning, transforming, and visualizing 
- Modeling 
- Evaluating and concluding 

## 2. Datasets

Our data comes from the [London Datastore](https://data.london.gov.uk/): a free, open-source data-sharing portal for London-oriented datasets. 

## 3. Sourcing and loading

<p align="center">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img1.png">
</p>

## 4. Cleaning, transforming, and visualizing

<p align="center">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img2.png">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img3.png">
</p>

In order to limit the number of data points I have, I will extract the year from every month value from the *Month* column. 

A lambda function will be used, following the following pattern:

1. Looking through the `Month` column
2. Extracting the year from each individual value in that column 
3. Storing that corresponding year as separate column. 

A reminder of the initial brief: which boroughs of London have seen the greatest house price increase, on average, over the past two decades? 

<p align="center">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img4.png">
</p>

## 5. Modeling

Creating a function that will calculate a ratio of house prices, comparing the price of a house in 2018 to the price in 1998.

This function will be called: create_price_ratio.

The following steps will be undertaken: 

1. Take a filter of dfg, specifically where this filter constrains the London_Borough, as an argument. 

2. Get the Average Price for that Borough, for the years 1998 and 2018.

4. Calculate the ratio of the Average Price for 1998 divided by the Average Price for 2018.

5. Return that ratio.

Then, iterating through all the unique London_Boroughs and working out the ratio capturing the difference of house prices between 1998 and 2018 will be carried out.

<p align="center">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img5.png">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img6.png">
</p>

## 6. Evaluating and Concluding

<p align="center">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img7.png">
  <img width="600" height="300" src="https://raw.githubusercontent.com/mohamedziane/London-Housing-Prices-by-Borough-1998-to-2018-/main/images/img8.png">
</p>

- Hackney has shown the greatest price change among all of the London boroughs with ~6.2% when comparing 1995 with 2018.

- From 1995 until 2015, Hackney has shown the highest demands due to:
    - Affordability: Low house prices compared to other London Boroughs (Affordable to the middle class).
    - Easy Access to the city of London.
    - Explosion of new developments and boutique-style businesses.
    - Big demand spike in 2012 only in Hackney, after the 2008 Financial crisis, mainly because it was one of the 5 cities in London hosting the Olympic Games in 2012.

- From 2015 to date, all London borough have shown a decline in house sales:

After analyzing both the Average Price and the Sales Volume sheets we can conclude that when the demand curve for housing increases, so too do prices. It makes sense: If more people want something that is available for purchase (low supply), then they are willing to pay more for that product. As prices increase, demand generally drops, as affordability decreases.

- There are so many factors that can affect the supply and demand for housing, and many aren't economic in nature.

Consider the current COVID-19 pandemic, which grounded constructions, paused home sales for a period, and caused building materials to be intermittently (un)available. That certainly put significant downward pressure on housing supply and demand. Or, consider a local government that wants to encourage urban growth and opens up new urban land for development that will increase supply as inward migration increases demand. So as a conclusion, we can not look at only the price increase change without looking at many different factors that affect housing market supply and demand like in our example the Sale volumes.
