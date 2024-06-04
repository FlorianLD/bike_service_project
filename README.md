# bike_service_project
Data project about the public bike service traffic in New York.

# Objective

This is a data project I made when I learned to use [seaborn](https://seaborn.pydata.org/) and [matplotlib](https://matplotlib.org/) libraries.<br>
The objective was to rely entirely on those two libraries to create data visualizations.<br>
See notebook [here](https://github.com/FlorianLD/ai_data_cleaning/blob/main/ai_data_cleaning.ipynb).

# Tools

- [pandas](https://pandas.pydata.org/)
- [seaborn](https://seaborn.pydata.org/)
- [matplotlib](https://matplotlib.org/)
- [requests](https://requests.readthedocs.io/en/latest/)

# Material

The material used is a csv file with data from [Citi Bike](https://citibikenyc.com/), a bike services company from New York.<br>
Data used for this project is from January 2023 ([source](https://citibikenyc.com/system-data)).<br>
The file consists of several columns with information such as:
- ride IDs
- station names
- date and time for departures and arrivals
- latitude/longitude coordinates
  
![Test](/dataset.png)

# Context

Managing traffic flows is one of the main challenges of civil engineering, hence why usage of data and especially real time data is essential to better understand the patterns of traffic flows.<br>
In a metropolis like New York, road traffic can change heavily with weather conditions, national holidays, seasons, events, public renovations.<br>
Over the last decade, public bike services have grown popular as a commuting mean, changing the way road network is designed.<br>
By leveraging public bike services data, we can better understand how people use this service and what they expect from it.
Analyzing this data is crucial to adapt capacity and density of the bike service, so that it suits users' needs and habits.


# Data

Data was prepared to enable the creation of the visualizations below:
- duration distribution
- hour frame distribution
- weekday distribution
- usage/distance relation



## Duration distribution
Bar chart displaying the distribution of rides by duration categories.

![Test](/duration_chart.png)

Three categories were created:
- 0 to 5 minutes, representing "short" rides
- 5 to 10 minutes, representing "medium" rides
- 15 minutes and over, representing "long" rides

This visualization shows the high level data of usage habits and highlights the prevalence of medium-length rides.<br>


## Hour frame distribution
Line chart displaying the mean value of ride departures by hour frame.

![Test](/hour_frame_chart.png)

The goal was to get insights about the evolution of traffic throughout the day, showing which hour frames had the highest traffic and which had the lowest.<br>
This line chart uses the aggregated values of the dataset to display the mean value for each hour frame. Additionnally, a confidence interval is displayed around the line, showing the estimation range for data points.<br>
This type of visualization can be crucial to assess the capacity of each station throughout the day.

## Weekday distribution
Bar chart displaying the distribution of rides by day of the week, with a confidence interval showing an estimation range.

![Test](/weekday_chart.png)


## Usage/distance relation
Scatter plot displaying the 10 ride routes with the most rides.<br>
A ride route is defined as a ride starting from a station A and ending at a station B.

Below is a dataframe with the 10 most used ride routes.

![Test](/most_popular_routes_df.png)

Since the dataset only contains latitude and longitude coordinates, the distance was calculated using [Google Maps Routes API](https://developers.google.com/maps/documentation/routes). The benefit of this step was to retrieve the actual distance, taking into account the road network for more precise distance calculation.


![Test](/google_maps_api.png)

Once the distance values are retrieved, data can be plotted on a scatterplot to display the 10 most popular routes.

![Test](/relation_chart.png)

When scaled to a complete year and to all the ride routes, this type of visualization can help us understand the overall usage habits of the bike service users.
Leveraging this data would also be valuable to better manage the existing stations and estimate the best areas to target in the creation of new stations.

