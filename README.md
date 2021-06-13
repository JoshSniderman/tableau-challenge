# tableau-challenge

## Introduction

The purpose of this report is to visualize historic rental bike data in New York City in order to search for trends that can lead to actionable insights. In a large city such as New York a diverse array of transportation options will always be necessary to serve the population and keep traffic congestion to a minimum. Bike rentals are one option of many and should be encouraged because of the availability of bike lanes and the benefit of being an environmentally friendly selection.

For the purposes of this assignment, I chose to complete two tasks:
- Break down the distribution of ages by region of the New York City area.
- Show the percentage of users returned the bikes within the time restriction set by CitiBike's service.

Full CitiBike Story can be found at https://public.tableau.com/app/profile/josh.sniderman/viz/CitiBike_Analysis_16219772087340/CitiBikeStory

## Data Preparation

Datasets used includes data for rentals from January, Feburary, March, and April of 2021 (four months of data).

Before we can begin preparing visuals, we must fix the data to make our tasks possible. Using the map visual and the lasso tool, we can group the locations into four regions : Manhattan, Brooklyn, Queens, and the Bronx.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![full_map](Images/full_map.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Prediction 1: 
### Ages in each regions will peak near millennial birth years (1985 - 1994).

We believe that most rental bike users in the New York City area will be millenials, being born in and around years 1985 to 1994.

To see the distribution of ages in the regions, we have created a dashboard:

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![full_age](Images/full_age.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

As we can see from this visualization, we have found our ***first anomaly***, a large spike of data entries in the years 1969 and 1970. As we see on the dashboard, 72.93% of all data points fall within these two years. Since it would be unrealistic that this many people would be born in a single year, we must make another assumption as to why there are so many data entries for this birthyear.

When we look at the data, we see that there are no ***null*** values. Knowing that it is unlikely that every single user has chosen to enter their birthyear for use of the service, we can assume that the users who chose not to give CitiBike their personal information simply left this field on the default value, which must have been 1970. It is much more likely that 72.93% of users simply did wish to fill in this information, than 72.93% of users be born in a single year.

Unfortunately, there is not an easy way to determine which users were actually born in 1970, and which were only default valued entries. For this reason, for the purposes of our analysis, we must exclude all values from the birthyears 1969 and 1970 to see a more accurate look of age distribution. 

The folowing dashboard uses data excluding birthyears 1969 and 1970. We can clearly see the gap in the lower left visual, but it is safe to assume a straight line connecting the data around the gap:

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![filtered_age](Images/filtered_age.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

As predicted, majority of birthyears in millennial birthyears, with 36.94% of datapoints falling within the bounds of 1985 to 1994, with peaks at 1990 for Manhattan, Brooklyn, and Queens, and peak at 1988 for the Bronx. An overall peak at 1990 can be seen below when isolated:

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![filtered_age_isolated](Images/filtered_age_isolated.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Prediction 2: 
### Most rentals will be returned within the allowed time established by CitiBkie’s service.

According to citibikenyc.com, Day Passes are restricted to 30-minute trips, and annual subscriptions are restricted to 45-minute trips.

Using user standing, line graph Durations of Usertype created

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![full_user_stand](Images/full_user_stand.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Anomaly 2: Data with extreme time durations, some as high as over 800 hours
Assumed to be Bikes either used for extreme periods of time, or bikes were stolen

Data points over 1 hour are so insignificant, the are not necessary to put onto the visual. Therefore, will be excluded for easier readability on User Standing by Usertype

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![filtered_user_stand](Images/filtered_user_stand.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

As we see on the dashboard, large humps in good standing data, with significant declines before becoming overdue, proving our prediction.

Over 98% Subscribers good standing, but only 88% of customers, most likely tourists, which makes sense.

One interesting point: if isolating users from the 1969-1970 spike from the previous exercise, almost exclusively Customers

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![user_dash_without_spike](Images/user_dash_without_spike.png)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Taking what we concluded from the previous section about 1970 being essentially a null value, this would make sense, as Subscribers are more likely to fill in personal information, whereas one-time customers will certainly skip out on filling out forms.
