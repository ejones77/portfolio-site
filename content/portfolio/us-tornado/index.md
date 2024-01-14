---
title: US Tornado Dashboard
description: Interactive Streamlit app with historic tornado data
date: "2023-12-14"
jobDate: 2023-12-14
work: [Data Visualization]
techs: [Python, Streamlit, Plotly]
thumbnail: ../../images/F5_tornado_Elie_Manitoba_2007.jpg
projectUrl: https://github.com/ejones77/tornado_app

---
*"File:F5 tornado Elie Manitoba 2007.jpg" by Justin Hobson (Justin1569 at English Wikipedia) is licensed under CC BY-SA 3.0.* <br><br>

Using Streamlit, Geopandas, and Plotly, I developed an interactive application to visualize US tornado data from 1950-2021.

This <a href="https://us-tornado-app.streamlit.app/" target="_blank">dashboard</a> utilizes custom GeoJSON objects pertaining to US State and Territory boundaries to display 71 years of tornadoes, complete with filters for state and magnitude. 

Summary statistics and aggregated visualizations show which states have experienced the worst tornadoes. 

A secondary page provides comparisons between two states using statistical testing to compare which state has a higher average tornado rate, as well as within each state, a comparsion from before and after the year 2000. 

Streamlit might take a while to boot, so I'll include the feature chart below!
<br>
<br>
<div class="center-iframe">
<iframe class="iframe-chart" src="../../charts/tornado-map.html" width="1000" height="800"></iframe>
</div>