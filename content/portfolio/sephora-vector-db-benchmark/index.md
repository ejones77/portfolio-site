---
title: Sephora Vector Database Benchmarking
description: Evaluate Pinecone, MongoDB, and ElasticSearch VectorDB performance on CRUD operations using a dataset of 90,000 Sephora Reviews
date: "2023-12-03"
jobDate: 2023-12-03
work: [Machine Learning]
techs: [Python, Pandas, Transformers]
thumbnail: ../../images/sephora_times_square.jpg
projectUrl: https://github.com/ejones77/sephora-reviews

---

*"Times Square Sephora" by m01229 is licensed under CC BY 2.0.* <br><br>

As part of a class on database preparation and management at Northwestern, I put together a benchmark test for 3 vector DBs using 90,000 Sephora product reviews. 

MongoDB was ultimately recommended for its expansive functionality, easy setup, and accessible documentation. It's fastest at reading records and in the middle when it comes to creating records. Those two operations are more important for a product review engine. 

Below are the results that were compiled after running three trials for each database: 


<br><br>

<img class="image-chart" src="../../images/Fastest Database per Question (seconds).png" alt="Trial question results for each DB">

<br>

<br>

<img class="image-chart" src="../../images/word_cloud_sephora.png" alt="Word cloud of Sephora product reviews">

<br>

<br>

<img class="image-chart" src="../../images/Average Create Time (seconds).png" alt="Average create time across 3 trials">

<br>

<br>

<img class="image-chart" src="../../images/Average Delete, Update, Read Times (Seconds).png" alt="Average delete, update, read time across 3 trials">

<br>

<br>

<img class="image-chart" src="../../images/Create Time per Trial (seconds).png" alt="Create time in each trial">

<br>

<br>

<img class="image-chart" src="../../images/Delete Time per Trial (seconds).png" alt="Delete time in each trial">

<br>

<br>

<img class="image-chart" src="../../images/Read Time per Trial (seconds).png" alt="Read time in each trial">

<br>

<br>

<img class="image-chart" src="../../images/Update Time per Trial (seconds).png" alt="Update time in each trial">