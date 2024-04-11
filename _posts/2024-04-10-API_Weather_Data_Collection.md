---
title: "API Weather Data Collection"
date: 2024-04-10
---

# TL;DR

In my first post, I would like to share the script that accesses through API the weather database, and retrieves the weather data for a particular location every 5 minutes. It writes them down in a text file in a format, friendly for a further analysis.

# Detailed Description

These scripts were created when we deployed PROSPECT reactor neutrino experiment at the Oak Ridge National Lab. I was assigned to look at the correlation of the neutron rates from cosmic rays with atmospheric pressure and other environmental parameters.


At the time, we did not have the access to the pressure data around Oak Ridge (or we thought we did not), and I was looking for ways to obtain these datasets from online. One of the ways I discovered was to utilize website OpenWeather through the API requests. OpenWeather has a variety of options of subscriptions for different datasets, including historical datasets. The free ones, however, include current weather and simple forecasts for 5 days. The maximum call per minute that is given with a free access is 60.


![alt text](https://github.com/olgakyzylova/blog/blob/main/_posts/imgs/Picture1.png "Screenshot of Free Plan on OpenWeather Website")


The first step is to create a free account using your email. After registration, you obtain your unique API key. OpenWeather allows you to get weather at any point on the globe – you will only need to write down latitude and longitude of location (it was a zip code in 2018). Here I used Blacksburg, VA, as an example – the longitude and latitude of Blacksburg are 37.23 and -80.41, correspondingly. We insert it in the link, together with provided to us API key:


![alt text](https://github.com/olgakyzylova/blog/blob/main/_posts/imgs/Picture2.png "Html link of API request")


And this is the result we are getting when calling for current weather in Blacksburg:


![alt text](https://github.com/olgakyzylova/blog/blob/main/_posts/imgs/Picture3.png "Result of API Request from OpenWeather")


For PROSPECT experiment, we only cared about absolute time (dt) and pressure (pressure), and also humidity at the time; however, as you can see, we could also extract other parameters such as wind, visibility, clouds. In my script, I collect all of them.



The script is written in python, and is sending API requests every 5 mins, while reading the results into a text file for a further analysis.
