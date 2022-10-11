---
layout: post
title:  Project Proposal
date:   2022-10-10 13:00:00 -0700
---
# Problem Space and Applications
As the climate changes, we have started to notice changes in the living quality of all people. We see
that for entire months of the year, forest fires cause a haze of smoke to descend and stay on Seattle.

Many people especially in the Seattle area have outdoor activity habits such as hiking or outdoor 
running on weekends. In this case, an air quality measurement system would be an effective way that 
helps people to be aware of the clearness of the air in each area they are going to.   

We aim to give people data about the air they have been breathing. We want to give people the ability
to see historical data about the quality and location of those measurements. Our measurement device 
will be a puck, with built-in air quality sensors (for particulates PM2.5), minimum one-day battery 
life, and a connection to your mobile phone that you carry.

# Example Scenarios
An example scenario would be a person in a heavily air-polluted area being able to see historical 
data over both time and location of air quality. The project should be able to create tracks of the data.

# Related Technology
[Purple Air](https://www2.purpleair.com/): Purple Air provides a similar service, aggregating data 
with static sensors that you can buy, aggregating data and serving it through both an API and a map.

![Purple Air AQI map](/cse475-22au-docs/assets/proposal/purple-air-map.png)

![Air Gradient](https://www.airgradient.com/open-airgradient/instructions/diy/). Again, another static 
sensor. In contrast with Purple Air, this is more DIY and lower cost.

# Potential Design Solutions
We are planning to use a NodeMCU microcontroller, which has a built-in WiFi chip and will allow the 
sensor to easily transmit data to a phone.  To increase the battery life of our device, we will only 
collect data at certain intervals as opposed to constantly transmitting air quality readings.  

# Needed Resources
We anticipate that finding a low-power air quality sensor will be difficult (power, heat).

# Demo
By the end of this class we will be able to demonstrate a working wearable sensor that will send air quality data to a mobile phone and allow the user to see the air quality data on a map. 

