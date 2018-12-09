# Personal Interface Requirements

We define here the requirements for the personal interfaces we decided to implement.
The smartphone app we were going to design must fulfill some requisites:
	1) Summarize all the information in an easy-to-use tool.
	2) Provide readable data about the behavior of a certain variable in time.
	3) Allow the most curios users to confront data between the/some stations.

Build such a thing is not an easy task, given that the space is small and so you have to optimize it, to display in the best quality possible those data that the users
expect to see.
The smartwatch app cannot be as full of details as the smatphone's, given the more restricted space, it will only visualize the last measurements an a brief daily history-


# Projects already implemented
The first step before even thinking about the app design was research.
We looked for similar apps and research papers/articles/anything that could be useful to our project. 
As for the mobile apps, we found some pretty inspiring examples.
We will focus on Mobile Apps, Desktop applications and ambient display that we can use and analyze.

## Mobile Apps


the first application that we are analyzinig is AirVisul, available on the Play store and Apple store.  
Air Visual is specialized in displaying informations about ari qualityusing a clean and easy-to-use interface.

We found this summary very helpful to have a quick glance on the situation of the air pollution in a certain area q

![](./Screenshots/AirVisual1.jpeg "main")

This is the main interface of AirVisual, as we can see the first thing that we notice is the summary of the air quality in a specific city.  
The specific parameters are hidden for now to give allow the user to "zoom out" on the air quality in a city.  

in our application we thought about implementig an histogram to visualize the data within a time window and the max value registered in a year.

![](./Screenshots/AirVisual2.jpeg "main")

Swiping down we can see a more detailed view about the air quality in the selected city, showing a Daily/Hourly information about it.

![](./Screenshots/AirVisualMap.jpeg "main")

Another feature of the application is to show the map of our surroundings, linking the data about the air quality to the cities near you.

![](./Screenshots/Graphicinrespecttotime.jpeg "main")



#Smartwatch app resources 
Papers 
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5038811/
 

REASONING ON THE DATASET
Given the variables the station is measuring and what has to be shown through the interfaces, we have defined a simple hierarchy of the information.
We decided to divide them in two groups:
VARIABLES strongly dependent on location, and immutable/less important data
-Weather(and Pressure)
-Hour, season
-Wind direction
-Location features
IMPORTANT variables, more likely to be studied and with some kind of behaviour
-CO2 ppm
-Wind speed
-Luminosity
-Temperature
-Umidity
-Rain
We started building the interfaces based on this hierarcy, given more details for the most important variables.


APP GENERAL DESING

#SMARTPHONE

The user can visualize the data in more detail respect to the public interface.
This is useful to confront singles variables with respect to the nearest station with a map, or to a have a quick history of variables in time.
If the smartphone reach the range of the beacon nfc proper to all station, a notification will be sent to the smartphone, advising the user of the approach to the station and if the critical variables are dangerously high or not(with respect to mean), changing the default station we want to visualize into that particular one.

USER INTERACTION
At the opening of the app, three things can happen
    1) The user is not in the proximity of a eco station, so a map will be visualized with the nearest ecostation(1-2 km range) and the user will choose what station visualize
    2) The user is near a station, presses the notification, the app will open up and the air condition activity of that particular  will open up
    3) The user is near a station, opens the app in the standard way and a popup will show up(You are near to "Vega ecostation", connect to it?).

When a station is selected, the general display of that station will be visualized, that contains:
-Station name
-Time and season
-Weather around that particular station
-Type of soil and enviroment
-Height in maslm

If the user presses the data button, the icons of the most important variable will show up, with their current lecture already visible.
When an icon is pressed, the activity of that certain variable will popup up, in which the user can see how the last lecture approaches the annual max measure of that particular variable, as well as the behaviour of that variable in time(daily, monthly or annualy).
If the "Comparison" button is pressed, another activity will show up, which presents the comparison of actual lectures of the nearest stations and their behaviour in a week timespan.
THe user can return to the menu with the left top screen error on the variable-related activity


DATA REPRESENTATION TECHNIQUES
We use a lot of Icon representation for simplify the variables and how the user can immediately guess the meaning of all the data.
The charts we are going to use in the smartphone apps are:
-Histogram charts
-Gauge charts
-Map chart
-Line chart

The most important data that we thought as most important and provide some more information and history on the lecture are:
CO2 ppm
Air humidity
Wind speed 
Temperature
Rain
The histogram chart and Line chart will be visualized after having clicked on the gauge charts of a variable, another "activity" will be visualized with the istogram of the variable in a 15 day timespan and a line chart 
with the lecture of the other near station(always 1-2 km in range) and the selected one(confrontation).
To se the possible relation between different variables the technical application is suggested.

GAUGE CHART
The gauge chart is used to give an easy and pretty visualization to the raw data of the variables.
The max gauge will max value registered by the eco station in a year timespan for that parameter(for temperature will be the max related to the season, in order to have a more clear representation of that particular variable).

HISTOGRAM CHART
It's used to have a clear view of the behaviour of that particular variable in a certain timespan(can go from hours to days, can't say for sure what will be the most useful at the moment).
Of course data like pressure which is not subjected to clear changes and useless data like time or season will not be visualized.
We use it to better present the history of a certain variable and a visible difference between the other station current measures

LINE CHART
It will be visualized with the Histogram chart.
This confronts the different lectures of that particular variable in the SAME exact moment but in different days(Let's say that i open the app at 2:30 PM, this will show the last lectures (which are periodic).If i wanna confront these same lectures with other stations
and have a days timespan, I have to take the lectures of the exact same lecture but done the day before).
This might get out of hand when there are four or more station near by but given the kind of data the station is checking, it's highly improbable that situation will present.

MAP CHART
This is just to select the station from which we want to visualize the data from, each station has a cursor that has as id the name of the station.

#SMARTWATCH

For the smartwatch, which is a simple device, we decided not to provide lots of data or difficult plots that might result not clear to the user.
We represent only the most important variables, with a little overview of the location of the station, which is represented with a Modular Large Complication.
The navigation of the app will be a page-based one, with a total of 7 pages (one for each important variable + 1 for station overview).
The user can swipe through the pages, and in a page representing a variable, a double tap on the radar chart can change the type of data representation the page will visualize.

We use only two simple types of charts, given the restricted view of the device.
RADIAL CHART
We use it to visualize the current variable measurement with respect to a daily/montly/annual max value
HISTOGRAM CHART
Is a simple plot that can give a quick view to a short history of the variables, in order to extract possible behaviors of a certain variable.









