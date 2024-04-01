# Project Python Foundations: FoodHub Data Analysis
## Context
The number of restaurants in New York is increasing day by day. Lots of students and busy professionals rely on those restaurants due to their hectic lifestyles. Online food delivery service is a great option for them. It provides them with good food from their favorite restaurants. A food aggregator company FoodHub offers access to multiple restaurants through a single smartphone app.

The app allows the restaurants to receive a direct online order from a customer. The app assigns a delivery person from the company to pick up the order after it is confirmed by the restaurant. The delivery person then uses the map to reach the restaurant and waits for the food package. Once the food package is handed over to the delivery person, he/she confirms the pick-up in the app and travels to the customer's location to deliver the food. The delivery person confirms the drop-off in the app after delivering the food package to the customer. The customer can rate the order in the app. The food aggregator earns money by collecting a fixed margin of the delivery order from the restaurants.

## Objective
The food aggregator company has stored the data of the different orders made by the registered customers in their online portal. They want to analyze the data to get a fair idea about the demand of different restaurants which will help them in enhancing their customer experience. Suppose you are hired as a Data Scientist in this company and the Data Science team has shared some of the key questions that need to be answered. Perform the data analysis to find answers to these questions that will help the company to improve the business.

## Data Description
The data contains the different data related to a food order. The detailed data dictionary is given below.

## Data Dictionary
- order_id: Unique ID of the order
- customer_id: ID of the customer who ordered the food
- restaurant_name: Name of the restaurant
- cuisine_type: Cuisine ordered by the customer
- cost: Cost of the order
- day_of_the_week: Indicates whether the order is placed on a weekday or weekend (The weekday is from Monday to Friday and the weekend is Saturday and Sunday)
- rating: Rating given by the customer out of 5
- food_preparation_time: Time (in minutes) taken by the restaurant to prepare the food. This is calculated by taking the difference between the timestamps of the restaurant's order confirmation and the 
  delivery person's pick-up confirmation.
- delivery_time: Time (in minutes) taken by the delivery person to deliver the food package. This is calculated by taking the difference between the timestamps of the delivery person's pick-up confirmation and drop-off information

### Let us start by importing the required libraries

```
# import libraries for data manipulation
import numpy as np
import pandas as pd

# import libraries for data visualization
import matplotlib.pyplot as plt
import seaborn as sns

```
### Understanding the structure of the data

```
# read the data
df = pd.read_csv('foodhub_order.csv')
# returns the first 5 rows
df.head()
```


|    | order_id | customer_id | restaurant_name           |	cuisine_type | cost_of_the_order | day_of_the_week | rating    | food_preparation_time | delivery_time |
| -- | -------- | ----------- | ------------------------- | ------------ | ----------------- | --------------- | --------- | --------------------- | ------------- |
| 0  | 1477147  | 337525      |	Hangawi                   |	Korean       | 30.75             | Weekend         | Not given |	25	                 | 20            |
| 1  | 1477685  | 358141      |	Blue Ribbon Sushi Izakaya |	Japanese     | 12.08             | Weekend         | Not given |	25	                 | 23            |
| 2  | 1477070  | 66393	      | Cafe Habana               |	Mexican      | 12.23             | Weekday         | 5	       |  23	                 | 28            |
| 3  | 1477334  | 106968      |	Blue Ribbon Fried Chicken |	American     | 29.20	           | Weekend	       | 3	       |  25	                 | 15            |
| 4  | 1478249  | 76942       |	Dirty Bird to Go	        | American     | 11.59	           | Weekday         | 4	       |  25                   | 24            |

### Observations
#### The DataFrame has 9 columns as mentioned in the Data Dictionary. Data in each row corresponds to the order placed by a customer.

### Question 1: Write the code to check the shape of the dataset and write your observations based on that.
```
df.shape
```

