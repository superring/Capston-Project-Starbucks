# Udacity Capstone Project: Starbucks

Final project for Udacity's Data Scientist Nanodegree.

## Installation

In order to run the Jupyter notebook you will need to have python 3 installed and the following dependencies:

- [pandas](https://pandas.pydata.org/)
- [Numpy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)

## Project Motivation

In this project I conducted a exploratory analysis of the simulated data provided by Starbucks, to find out how people make purchasing decisions based on the discount or coupon offers they received. I also build a prediction model with FunkSVD algorithm to predict the responsiveness of the users toward the offers.

There are 2 questions we are interested:

1. Which offer should be sent to a particular customer to maximize the offer's sales gain?

2. Which demographic groups respond best to which offer type?


## File Descriptions

The analysis and predictive models are available in the Jupyter Notebook.

The datasets are a simplified version of the real Starbucks app because the data only contains information regarding one product whereas Starbucks has a whole line of products.

The data given to us was stored in 3 json files:

- `portfolio.json` - containing offer ids and data regarding the offer: duration, difficutlty and type.
- `Profile.json`  data containing demographic information for each customer.
- `transcript.json` - data containing every record for transaction, offers recieved, offers reviewed and offers completed.

Here are the schemas for each file:

`Portfolio.json`

- offer_id (string) - offer id
- offer type (string) - the type of offer: Informational, Discount, BOGO.
- difficulty (int) - minimum required to spend to complete an offer.
- reward (int) - the reward is given for completing the offer.
- duration (int) - time for the offer to be open in days.
- channels (list of strings)

`Profile.json`

- age (int) - age of the user
- become_member_on (int) - integer referring to the date the customer created an account.
- gender (string) - gender of the customer (Male, Female, Other)
- id (str) - customer id
- income (float) - customers income

`Transcript.json`

- event (string) - record description (transaction, offer received, offer completed, offer viewed)
- person (string) - customer_id
- time (int) - time in hours since the start of the test. 
- value (dictionary containing strings) - contains either offer id, amount or reward depending on the event.

## Results

The main findings of this project can be found in my medium post about the project [here](https://johnabel1997.medium.com/starbucks-capstone-challenge-350575a03f9a).

I build a user-offer-matrix based on the transcript records, and then split the records into the training set and the test set and trained the FunkSVD model to predict how a user responses to a particular offer. The mean squared error of the trained user matrix and offer matrix is around 0.0015, and the squared error of the test prediction is around 0.1327.

In the exploratory analysis of the responsiveness from different demographic groups to the offers, I found that females respond better than males in both BOGO and discount. Also I found taht people tend to response to social channel better than mobile, email and web. I also found that people with higher income tend to respond better than those with lower income. Also among all the income levels, except those with 80000+$ income, tend to discount better than BOGO. The last finding is that younger people less than 30 years old tend to respond worse than older people.

## Licensing, Authors and Acknowlegements

Thansk Starbucks and Udacity for providing the data in this project.






