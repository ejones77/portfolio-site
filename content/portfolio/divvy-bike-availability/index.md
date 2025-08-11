---
title: Divvy Bike Availability (WIP)
description: Predicting the availability of bikes at Divvy stations across Chicago
date: "2025-08-10"
jobDate: 2025-08-10
work: [Machine Learning]
techs: [Python, Go, AWS Sagemaker, Docker]
thumbnail: ../../images/Divvy_bikes_in_Chicago.jpg
projectUrl: divvy-bike-availability.us-east-2.elasticbeanstalk.com

---
*"Divvy bikes in Chicago" by Victor Grigas is licensed under CC BY-SA 4.0.* <br><br>

This project serves city bike availability predictions leveraging Go, Python, AWS resources, and a publicly available [live feed](https://divvybikes.com/system-data). 

The app is currently gearing up to be deployed on Elastic Beanstalk, Here's a quick look at the high level architecture:

<br><br>

<img class="image-chart" src="../../images/divvy-architecture.png" alt="Divvy availability architecture">

<br>

<br>

<img class="image-chart" src="../../images/divvy-cicd.png" alt="Divvy availability CI/CD">

<br>

<br>

So far things are working as expected locally, but I still have some deployment configurations to set straight at the time of writing. 

You can see how this is starting to shape up. The idea is that users can see both the current availability and future predicted availability together in one map.

<br>

<br>

<img class="image-chart" src="../../images/divvy-avail-screengrab.png" alt="Divvy availability CI/CD">