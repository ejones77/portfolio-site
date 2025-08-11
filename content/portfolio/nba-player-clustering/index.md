---
title: NBA Player Clustering
description: Exploring patterns in basketball data using unsupervised machine learning.
date: "2024-08-11"
jobDate: 2024-08-11
work: [Machine Learning]
techs: [Python, Pandas, Seaborn, sk-learn]
thumbnail: ../../images/nba.jpg
projectUrl: https://github.com/ejones77/nba_player_types

---
*"2013 NBA Logo" by RMTip21 is licensed under CC BY-SA 2.0.* <br><br>


A machine learning framework to reclassify NBA players beyond traditional positions using 10 years of player data (2014-2024). 

I applied K-means clustering with PCA dimensionality reduction to identify 5 distinct player archetypes: Stars, Snipers, Painters, Shooters, and Protectors.

Key Technical Components:
- Processed 10 seasons of NBA advanced statistics, per-100 possession metrics, and shooting data
- Implemented weighted averaging based on minutes played to capture career performance
- Evaluated 20 clustering models using multiple validation metrics (Silhouette Score, Calinski-Harabasz Index)
- Used t-SNE visualization for cluster interpretation and radar charts for feature analysis

Business Application:
- Applied clustering framework to Chicago Bulls roster analysis
- Identified team composition gaps and recommended specific free agent acquisitions
- Built OLS regression model predicting team wins with 91.8% R-squared accuracy
- Analyzed four-factor model (shooting, turnovers, rebounding, free throws) to evaluate team performance

## Detailed Analysis Report

<iframe src="/reports/nba_report.pdf" width="100%" height="600px" style="border: 1px solid #ccc; border-radius: 4px;">
</iframe>

**[📄 Download Full Report](/reports/nba_report.pdf)**