# Prediction Classify Hotel Booking


<p align="center">
  <img src="http://travelplanner.co.in/images/hotel/hotel-main.jpg" />
</p>



## Table of Content
  * [Business Problem](#business-problem)
  * [Goal](#goal)
  * [Abstract](#abstract)
  * [The Data](#the-data)
  * [Analysis](#analysis)
  * [Modeling](#modeling)
    - [Experiment 1](#experiment-1-scalingnormalize-the-data-using-minmaxscaler-and-do-hyperparameter-tunning-for-the-best)
    - [Experiment 2](#experiment-2-use-the-ensembles-method-and-use-hyperparameter-tunning-for-the-best-one)
  * [Final Model](#final-model)
  * [Conclusion](#conclusion)

## Business Problem 
Hotel cancellation rates have been steadily rising for years, in part fueled by a culture of ‘book now, pay later’ created by OTA giants. As a hotelier, it’s important for you to be aware of the patterns because it will help you to determine how to combat the issue. Back in 2019, D-Edge Hospitality Solutions reported that the [global cancellation rate of hotel reservations reached 40%](https://hospitalitytech.com/global-cancellation-rate-hotel-reservations-reaches-40-average)(with the direct website channel keeping the lowest cancellation rate). It’s imperative as a hotelier that you do not ignore this growing behaviour, it’s crucial you use all the tools at your disposal to minimise the upset to your revenue.


## Goal
This project applies basic machine learning concepts on data collected to make prediction models to classify a hotel booking׳s likelihood to be canceled. This project aims to develop a model to classify whether hotel booking is to be canceled or not. 


## Abstract
The purpose of this report will be to use the Trivago Booking Data to classify hotel bookings into possible canceled bookings or retained bookings. This can be used to gain insight into how and why bookings are canceled. This can also be used as a model to gain a marketing advantage, by advertisement targeting those who are more likely to retain their bookings or saving money by not targeting the bookings that are most likely to cancel their bookings.

## The Data 

[The data was originally created and found by Nuno Antonio, Ana Almeida, and Luis Nunes for the following paper](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/iscancaled.png?raw=true)


[You can access and download the data set from Kaggle](https://www.kaggle.com/jessemostipak/hotel-booking-demand/activity)

In this project, I' am not using all of the data. I just used 50.000 samples data.

## Analysis

- 37,1 % of customers in this data cancelled their reservations. 

Summarize the class distribution
:-------------------------:
![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/iscancaled.png?raw=true)

- The average of guests staying in the hotel is 3-4 days. The guest average stayed for one night on the weekend and stayed two nights on the weekdays.

- The cost average for every room is $102.00/night. Based on the graph below, we can see that the room price is quite volatile. And the room price always significantly increases every year.

The Average Room Price(EveryYear)           | The Average Room Price(EveryDay)   
:-------------------------:|:-------------------------:
![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/priceyear.png?raw=true)   | ![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/averagestayed.PNG?raw=true) 


- In general, we found that customers are more likely to cancel a booking when they have the following features:
  + Reserved a booking with a full-board meal.
  + Reserved a booking from the group's market segment.
  + Have no special requests.


Market Segment Percentag           | Meal Type Percentagee    | Total of Special Requests Percentage
:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/marketsegment.png?raw=true)  | ![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/mealtype.png?raw=true) | ![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/specialreq.png?raw=true)


- However, customers are more likely to retain a booking when they:
  + There are repeat guests.
  + Come from the following market segment:
    - Direct
    - Corporate
    - Complementary
    - Aviation
  + Are classified as a group customer type.

Market Segment Percentage           | Repeate Order Percentage    | Total of Special Requests
:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/marketsegment.png?raw=true)  | ![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/repeateguests.png?raw=true) | ![](https://github.com/docum5/Prediction_Classify_Hotel_Booking/blob/main/customertype.png?raw=true)



**These statistics can be useful for marketing towards customers, to increase booking retention, or they can be used to help a company focus on areas of improvement.**

## Modeling

### Experiment 1: Scaling/Normalize the data using MinMaxScaler and do Hyperparameter tunning for the best 

- Baseline

| Algorithm                  | Accuracy |
|----------------------------|----------|
| LogisticRegression         | 0.73     |
| LinearDiscriminantAnalysis | 0.73     |
| KNeighborsClassifier       | 0.92     |
| GaussianNB                 | 0.69     |
| SVC                        | 0.92     |

- With Hyperparameter Tunning

| Algorithm            | Accuracy |
|----------------------|----------|
| KNeighborsClassifier | 0.94     |
| SVC                  | 0.95     |



### Experiment 2: Use the ensembles method and use Hyperparameter tunning for the best one 

- Baseline

| Algorithm                  | Accuracy |
|----------------------------|----------|
| AdaBoostClassifier         | 0.79     |
| GradientBoostingClassifier | 0.90     |
| RandomForestClassifier     | 0.93     |

- With Hyperparameter Tunning

| Algorithm              | Accuracy |
|------------------------|----------|
| RandomForestClassifier | 0.95     |


## Final Model 
Actually, in my opinion, there is no correct answer to what model to choose. Usually, we will choose the model that gives us high accuracy. Based on our experiment above, Support Vector Machine and Random Forest give us the best accuracy (0.95). 

**Which one between them should we take?**
The model that we choose depends on the goal of our project. In this project, I do more consider about to press the false-negative/FN (machine predict the customer will come, but in reality, the customer is canceled). 
**Why did I choose to press the false-negative?**
The aim of this model is to make more profit for the hotel business, or we just see from a business profit perspective. If the hotel can predict does the customers will be canceled or not:

If the customer is predicted to be canceled, the hotel should not prepare that much about the reservation(e.g.breakfast). So it will be saved the hotel money expense. 

## Conclusion
With this information hotels can, for example, contact clients that the model predicted will cancel in order to get a cancellation earlier - so they can have more time to resell the room. Or perhaps approach the client in a way to make them feel special and keep their reservation and therefore cancel the others he or she had made in other hotels in the same city.


## Software and Libraries
This project uses the following software and Python libraries:



![](https://forthebadge.com/images/badges/made-with-python.svg)

[<img target="_blank" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Scikit_learn_logo_small.svg/2560px-Scikit_learn_logo_small.svg.png" width=100>](https://flask.palletsprojects.com/en/1.1.x/) [<img target="_blank" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/NumPy_logo_2020.svg/440px-NumPy_logo_2020.svg.png" width=150>](https://numpy.org/) [<img target="_blank" src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Pandas_logo.svg/1024px-Pandas_logo.svg.png" width=200>](https://pandas.pydata.org/docs/getting_started/index.html) [<img target="_blank" src="https://matplotlib.org/stable/_static/logo2.svg" width=100 height=50>](https://matplotlib.org)
