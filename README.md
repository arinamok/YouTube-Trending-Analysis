# What Makes YouTube Videos Trend?
## An Analysis of U.S. Trending Videos

## Overview
This project explores what helps a YouTube video trend in the United States. Using the `USvideos.csv` dataset from Kaggle (40,000+ records), the analysis examines how engagement metrics, content categories, tags, and publish timing relate to early popularity.

The goal is to determine which factors matter most when a video gains traction quickly.

## Dataset
The data used in this project comes from the [YouTube Trending Video Dataset on Kaggle](https://www.kaggle.com/datasets/datasnaek/youtube-new), which contains U.S. trending video records from 2017–2018.

This analysis uses two main files:
- **`USvideos.csv`**: Contains metadata and engagement metrics for 40,000+ videos. It can be downloaded directly [here](https://www.kaggle.com/datasets/datasnaek/youtube-new?resource=download&select=USvideos.csv) (Kaggle login required).
- **`US_category_id.json`**: Provides the mapping for category IDs to their human-readable names. It can be downloaded directly [here](https://www.kaggle.com/datasets/datasnaek/youtube-new?resource=download&select=US_category_id.json) (Kaggle login required).

### Key Data Features:
The dataset covers U.S. trending videos from 2017–2018 and includes:
* **Engagement Metrics:** Views, likes, dislikes, and comment counts.
* **Temporal Data:** Publish time and trending date (used to calculate velocity).
* **Metadata:** Video categories, tags, and descriptions.
* **Settings:** Engagement toggles (comments or ratings disabled).

*Note: For performance and modeling efficiency, a cleaned random sample of 15,000 records was used for the final analysis.*

## Data Preparation
Preprocessing was completed in Python using pandas and NumPy.

Key steps:
- Converted timestamps into proper datetime format  
- Cleaned and reformatted tags  
- Handled missing descriptions  
- Examined outliers using percentile analysis  
- Standardized engagement features before modeling  

Engagement data was heavily right-skewed, with a small number of viral videos driving extremely high values.

## Modeling

Three approaches were used to analyze trending behavior:

### Linear Regression
Predicted the number of days between the publish date and the trending date.  
Results showed that category influences trending speed more than early engagement metrics.

### Random Forest Classification
Predicted whether a video becomes highly viral.

- Accuracy: 88.1%  
- F1 Score: 0.92  
- Top features: views, likes, comment count  

Early engagement metrics were the strongest predictors of virality.

### K-Means Clustering
Grouped videos based on engagement behavior.

Four distinct patterns emerged:
- Typical trending content  
- Low-engagement/niche videos  
- Highly positive viral videos  
- Polarizing videos with high dislikes and heavy discussion  

This shows that videos gain traction through both broad appeal and strong emotional reactions.

## Key Takeaways
- Views, likes, and comments are the strongest predictors of virality.  
- Category affects how quickly a video trends.  
- Trending videos vary significantly in audience response.  
- Controversial content can generate as much traction as widely liked content.

## Tools
Python, pandas, NumPy, scikit-learn, Matplotlib, Seaborn  
Jupyter Notebook / Google Colab

## Additional Materials

A detailed technical report and project presentation are available:

- 📄 [Full Analysis Report](link_to_pdf)
- 📊 [Project Presentation](link_to_ppt)
