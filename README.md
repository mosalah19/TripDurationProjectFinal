# TripDurationProject
## Abstraction
Building a model that predicts the total duration of taxi trips in New York City. We are working on a dataset released by the New York City Taxi and Limousine Commission, which includes pickup time, geographic coordinates, number of passengers, and many other variables, and we will talk about the details during the report.

## Motivations
The motivation behind building a model to predict the duration of a taxi trip within New York City is the great impact it has on both parties, namely the service provider and the customers   (  passengers  ) .
It provides the customer with all the following : 
1- Planning and improving the trip schedule
2- Adherence to appointments
3- In emergency situations, such as going to the hospital
It provides the service provider with all the following: 
1- Correctly allocate human resources
2- The ability to contribute to the development of the city by providing information that is useful to
1)	Planning roads and infrastructure for the future
2)	traffic management
3)	Improving transportation
   
## Problem Definition and understanding
#### build a model that predicts the total ride duration of taxi trips in New York City. Your primary dataset is one released by the NYC Taxi and Limousine Commission, which includes pickup time, geo-coordinates, number of passengers, and several other variables

## Data fields:
* id - a unique identifier for each trip
* vendor_id - a code indicating the provider associated with the trip record
* pickup_datetime - date and time when the meter was engaged
* dropoff_datetime - date and time when the meter was disengaged
* passenger_count - the number of passengers in the vehicle (driver entered value)
* pickup_longitude - the longitude where the meter was engaged
* pickup_latitude - the latitude where the meter was engaged
* dropoff_longitude - the longitude where the meter was disengaged
* dropoff_latitude - the latitude where the meter was disengaged
* store_and_fwd_flag - This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a connection to the server - Y=store and forward; N=not a store and forward trip
* trip_duration - duration of the trip in seconds
  
## Dataset Description
The competition dataset is based on the 2016 NYC Yellow Cab trip record data made available in Big Query on Google Cloud Platform. The data was originally published by the NYC Taxi and Limousine Commission (TLC). The data was sampled and cleaned for the purposes of this playground competition. Based on individual trip attributes, participants should predict the duration of each trip in the test set.

| model  | Train R2-score | validation R2-score |
| :---         |     :---:      |          ---: |
| Ridge | 0.7298 |0.7311 |
| Random forest	  | 0.8351l  |0.7972 |
| Content XGBRegressor  | 0.8108  |0.8056 |

Source:
Kaggle : https://www.kaggle.com/c/nyc-taxi-trip-duration/data

