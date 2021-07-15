San Francisco Bay Area Bike Share - Ford GoBike Data

The original files can be found here: https://www.kaggle.com/benhamner/sf-bay-area-bike-share 

For this analysis, I have used:
- The station.csv file
- the trip.csv file
- the weather.csv file

The purpose of this analysis is to get an overview of the Ford GoBike activity in San Francisco and to understand how San Francisco residents use this service. 

The Jupyter Notebook is organised as follow:

- Introduction
- Dataset Initial Analysis and cleaning 
- Exploratory Part
- Explanatory Part

Here are the different steps I have taken: 

INITIAL ANALYSIS AND CLEANING

1 - Reviewing the 3 data sets
2 - Joining the trip.csv with the temperature.csv
--> the weather data had ducplicated dates so I removed them to do a left join
--> The common key in both document was the date but the trip.csv was in a timestamp format with the hour
--> I first separated the timestamp into a date column and a time column to have a merging key
--> Using the merge function I left joined both document into a new dataframe
3 - Joining the station data to the newly created df
--> the trip.csv document includes both start station and end station which means that I had to join the station data twice to get the right information
4 - Formatting all the date data to be used in graphs
--> setting the main dates into datetime objects
--> extracting the day of the week, month, year and month-year format to perform my analysis
5 - Saving the final dataframe as a master csv 



EXPLORATORY PART

1 - Univariate analysis
--> average riding time
--> main departing cities, San Francisco city clearly stood out, I decided to review the main arrival cities
--> main arrival cities, San Francisco stood out again, I decided to further analyse the main routes later in the analysis
--> Analysing the "subscription" column to see what was available to GoBike users. More tha 84% were subscribers compared to pays as you go
--> I looked at monthly trends but it wasn't enough to conclude on seasonality.
--> I looked at daily trends and clearly saw that the weekdays were the busiest days. This seemed like it could be linked to working days so I decided to look at heatmaps of day of the week and hour of the day later in the analysis to confirm my hypothesis.
2 - Bivariate abalysis
--> I first reviewed the bike activity evolution over a time but the data did not show anything worth sharing
--> I then reviewed the number of rides in function of the weather and there seemed to be a correlation but it was too soon to confirm. I made a note and explored this further later.
3 - Multivariate analysis
--> I looked at the relationship between temperature and number of rides over a time and both lines followed the same trend. I also used the corr() function to confirm the correlation
--> I wanted to create a heatmap of bike usage during the day of the week and hour of the day to confirm my commuting hypothesis. The heatmap directly confirmed that the bikes were mainly used on weekdays in the morning and at the office closing time (after 4.30pm). I made a note to look at this data by user type to see how it might differ
--> I wanted to see if rainy days had a strong impact on the number of ride and found out that there had been a major flood on december 2014 and there was a 0.4 correlation coeff between the number of rides and the rain precipitation
-->I looked at the impact of wind but the correlation coeff was very low (0.06) so I did not investigate it further
-->I looked for the impact of visibility but the corr. ceoeff. was also low
-->I looked at the most common routes by concatenating the start city and end city into a new columns. This showed that most routes were intra-cities, with more than 90% in SF city

EXPLANATORY PART
After completing the exploratory part of my analysis, I built the following plan for my presentation
- Introduction to the activity of GoBike in San Francisco: This part would include the station distribution and their average bike usage, the ride duration for each cities 
- Usage Behavior: I wanted to show the high volume of subscribers and how their behaviour differed from the pay as you go customers
- Weather impact

I had already created the main graphs for these data, I simply had to use city data or user type data in my pivot tables and I formatted the graphs to make them clearer and I matched the color with the Ford GoBike logo. 

The main website I used for the formatting was: the python graph gallery which was well documented and had every type of graphs I could think of. https://python-graph-gallery.com



