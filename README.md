# Project Movie Dashboard
## Table of Content
- [Project Overview](#project-overview)
- [Data Sources](#data-sources) 
- [Tools](#tools)

### Project Overview
This data analysis project aims to provide insights into the performance and trends of movies from 2012 to 2016 to the team of creative directors of Apple TV. By analyzing various aspects of the movie data, we seek to identify patterns, make data-driven recommendations, and gain a deeper understanding of the industry's dynamics.

### Data Sources
Movie Data : The primary dataset used for this analysis is the  [Data Ready for Dashboard.xlsx](https://github.com/user-attachments/files/19432217/Data.Ready.for.Dashboard.xlsx)
 file, containing detailed information about each movie's performance (budget and box office), actors, directors, genres, ratings etc.

### Tools
- Power Query - I used Power Query for Data Cleaning
- Excel - for Data Analysis
  - Pivot Tables - for Creating Dashboard and Visualizations

### Data Cleaning/Preparation
- Data loading and inspection.
- Handling errors, missing values.
- Data cleaning and formatting.
The excel file after the data cleaning & preparation process can be downloaded here - [Ready_to_use_Dashboard](https://github.com/user-attachments/files/19431612/Dashboard_Excel.xlsx)

### Questions for Data Analysis
 1. Which top 10 genres were the most successful (box) these years?
 2. Which top 5 actors were the most successfull?
 3. Top 5 movies by Box and Budget?
 4. Seasonality?

### Dashboard
![Dashboard](https://github.com/user-attachments/assets/b15960f0-75a7-4609-96fb-9f48b838744f)

### Results and Findings
As an example of interesting findings: best profitable movie, with an ROI of 10080%, was horror movie "Devil Inside".
![TopProfitMovie](https://github.com/user-attachments/assets/90a7df26-520f-4f71-9cbe-8d5fc432bce8)

There were not many female profitable actors these years, but Jennifer Lawrence was the top 1.
![TopActors](https://github.com/user-attachments/assets/d7555633-5c92-4db7-b02a-d34d1089c259)

### Challenges
#### M Language 

One of interesting features I was working with was a specific code for Grouping in M language which enable me to Combine genres together for further analysis.

```

= Table.Group(#"Sorted Rows1", {"Movie Title"}, 

                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},

                                            {"AllData", each _, 

                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}

                                            }

```

