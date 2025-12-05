---
title: Divvy Bike Availability (WIP)
description: Predicting the availability of bikes at Divvy stations across Chicago
date: "2025-08-10"
jobDate: 2025-08-10
work: [Machine Learning]
techs: [Python, Go, AWS Sagemaker, Docker]
thumbnail: ../../images/Divvy_bikes_in_Chicago.jpg
projectUrl: https://github.com/ejones77/divvy-bike-map

---
*"Divvy bikes in Chicago" by Victor Grigas is licensed under CC BY-SA 4.0.* <br><br>

This project serves city bike availability predictions leveraging Go, Python, AWS resources, and a publicly available [live feed](https://divvybikes.com/system-data). 

It can be deployed on a single AWS EC2 instance, but currently takes a bit of intial setup to collect data and train a model based on the availability feed. 

This isn't currently deployed due to the cost it takes to support and maintain, but might return to this when the weather is warmer.

This was part of my Master's Degree in Data Science at Northwestern University for the class Data Science in the Cloud

<br><br>

<img class="image-chart" src="../../images/divvy-avail-screengrab.png" alt="Divvy availability CI/CD">


The Divvy Availability Predictor makes use of the company’s publicly available live stations feed, deploying a machine learning model that predicts the capacity rating for every bike station in Chicago. The application provides a toggle between current availability, and the predicted availability in six hours. The app provides city bike riders more confidence in their urban travel plans with an overlay of color-coded bike stations throughout the city. The application has two primary microservices deployed in an AWS EC2 instance.

<u>API</u>: The API connection to divvy is built in Go, which manages the collection of station capacity data and uploads to the postgres database every 15 minutes. The database is hosted in a serverless environment provided by Neon. The Go API also handles the connection between the front-end and the back-end of the application, which is displayed with server-side rendering in HTMX with a handful of helper functions in Javascript. 

<u>ML</u>: The ML service is built in Python, which handles data pre-processing, feature engineering, training and inference via XGBoost. This service also makes use of the database for the purpose of extracting training and inference data. The app will refresh predictions every two hours.

Both services have their own Dockerfile and are managed with Docker Compose. To orchestrate a smooth startup, a bash script fetches the trained model from AWS S3, and requires that an initial round of predictions is ready before startup. Prometheus and Grafana provide rich logging and monitoring capabilities, making it easy to understand what’s happening in the application, and where errors might arise. 

<br><br>

<img class="image-chart" src="../../images/divvy-architecture.png" alt="Divvy availability architecture">

<br><br>

**Advantages**: 

<u>Speed</u>: The build is relatively quick considering the scale of the data being ingested. With nearly 2,000 stations and each one being evaluated on a 15 minute basis, the amount of records consumed and stored grows quickly. Getting a trained model ahead of time rapidly accelerates the time to launch new deployments. 

<u>Model freshness</u>: The data collection isn’t cumulative, and the model doesn’t need it. Because the data grows so quick, it only takes a few days of data to produce a decent model. And for a successful application, you don’t need to store more than ~100,000-200,000 records at a time. 

Testing infrastructure: Each component of the application has robust unit testing that confirms core functionality is operating as intended. 

**Disadvantages**:

<u>Accuracy</u>: While there’s a fair amount of feature engineering and hyperparameter optimization, the model only predicts with ~82% accuracy. This could be improved with access to weather data. There’s years of historical data from Divvy also available publicly, however station IDs are not consistent nor unique between the live dataset and the historical dataset. It may be possible to reconcile this, but the process would be extremely difficult. 

<u>Go/Neon coupling</u>: DB migrations run as part of the Go service, which could pose an issue if the application is running between multiple instances. As part of the initial deployment, this is not the case, but this architectural decision will need to be revisited if the application were to scale. 

<u>Complexity</u>: The Go and Python services existing in tandem leverages the strengths of the two languages, but it also might produce unexpected behavior down the line. With two languages handling similar tasks, one change might create disruption.

<br>
