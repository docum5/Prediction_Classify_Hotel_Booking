# Prediction_Classify_Hotel_Booking
Prediction models to classify a hotel booking׳s likelihood to be canceled.

Goal
This project aims to develop a model to classify whether hotel booking is to be canceled or not.
Abstract
The purpose of this report will be to use the Trivago Booking Data to classify hotel bookings into possible canceled bookings or retained bookings. This can be used to gain insight into how and why bookings are canceled. This can also be used as a model to gain a marketing advantage, by advertisement targeting those who are more likely to retain their bookings or saving money by not targeting the bookings that are most likely to cancel their bookings.
The Data 
The data was originally created and found by Nuno Antonio, Ana Almeida, and Luis Nunes for the following paper:
https://www.sciencedirect.com/science/article/pii/S2352340918315191#t0040
You can access and download the data set from Kaggle [https://www.kaggle.com/jessemostipak/hotel-booking-demand/activity]
In this project, I' am not using all of the data. I just used 50.000 samples data.
Analysis
In general, we found that customers are more likely to cancel a booking when they have the following features:
Reserved a booking with a full-board meal.
Reserved a booking from the group's market segment.
Have no special requests.
However, customers are more likely to retain a booking when they:
There are repeat guests.
Come from the following market segment:
Direct
Corporate
Complementary
Aviation
Are classified as a group customer type.
These statistics can be useful for marketing towards customers, to increase booking retention, or they can be used to help a company focus on areas of improvement.

Experiment 1: Scaling/Normalize the data using MinMaxScaler and do Hyperparameter tunning for the best 

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



Experiment 2: Use the ensembles method and use Hyperparameter tunning for the best one 

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




