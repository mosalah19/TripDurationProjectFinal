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
   
## EDA Summary
   ### dataset
•	training dataset have 1000000 rows and 11 columns
•	7 columns include numerical values.
•	4 columns include object(text, date) values. 
•	Don’t have any null values or duplicated values.



###vendor id 
•	vendor id has two value 1,2
•	vendor ID 2 has made more trips than  vendor id 1
•	vendor ID 2 made 54% of trips.
•	The different vendors did not affect the average trip duration, so their values were very close

### Number of passengers 
•	71% of  trips had 1 passenger and 14 % trips  had 2 passengers and 5 % of  trips had 3 passengers.
•	There are two trips have 7 passengers.
•	 some trips that have zero passenger (38 trips)

### Longitude and latitude 
•	From longitude and latitude of start and end point can
extract new features distance
•	Distance has clearly outliers ,some trips have distance 771 kilo meters that is impossible. 
•	Trip duration and distance have high correlation, can you profit from it in your model.
### Note :
 Now have distance and trip duration ,can you extract new                                                                                            feature speed (speed = distance / duration )
store_and_fwd_flag:
•	90 %  of the trip not a store and forward trip.


### Speed:
•	Speed is computed by divide distance by trip duration. 
•	Can not used speed on your model but can get sum intuitions about correlated it with other features.


### date features:
•	The number of trips increases at noon and in the evening than at any other time.
•	The number of flights increases on Friday, Saturday, and         Thursday of each week.
•	The speed of vehicles increased between night and late at              night.
•	    The speed of vehicles increased on Sunday and Saturday
•	    The speed of vehicles increased in the months of 5 and 6
•	 The speed of vehicles increased on holiday days than on   other days.


## add new feature from The Open-Source Routing Machine (OSRM) dataset.
	There are many columns that can help him predict like total_distance , total_travel_time , number_of_steps 

	 You can also verify this by merging with the main dataset by column ID.


### Total distance :
•	total_distance has negative skew
•	most distance is between 0 and 5000 metre
        total travel time:
•	total travel time has negative skew.
•	most total travel time is between 0 and 16 minutes.
### number_of_steps:
•	number_of_steps have negative skew.
•	most number_of_steps is between 1.5 and 2.5 steps


model	               Train R2-score	       validation R2-score
Ridge	                   0.7298               	   0.7311
Random forest	           0.8351	                   0.7972
XGBRegressor	          0.8108	                   0.8056


