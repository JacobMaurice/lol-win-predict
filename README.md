# Purpose of This Project
## Background
This is my first coding project (still ongoing) and its purpose is simply to practice some of the concepts I have learned on Codecademy. My academic background is a BASc in Nanotechnology Engineering, where the limited amount of programming done was computational. I learned near the end of my degree that I enjoyed computer science and specifically wanted to spend some time learning the basics/fundamentals of data science and machine learning.

## League of Legends
To keep me motivated and interested, I decided to work with real-world data that I personally have an interest in.

League of Legends (LoL) is a highly popular multiplayer online battle arena (MOBA) video game developed and published by Riot Games. In LoL, players assume the role of a "champion," each with unique abilities, and compete in teams to destroy the opposing team's base while defending their own.

There are many reasons why League of Legends makes a good data science project:

Vast Amount of Data: League of Legends generates an enormous amount of data every day, including gameplay statistics, match results. This data can be collected from the game's API, online repositories, or directly from the game itself.

Complexity: The game is highly complex, with numerous variables influencing the outcome of matches. These variables include champion picks, item builds, player skill levels, team compositions, and neutral objectives.

Predictive Analytics: With access to historical match data, one can build predictive models to forecast match outcomes, player performance, or even trends in the meta (the most effective strategies and champion picks at a given time).

## Riot API
All the data used in this project was extracted from Riot APIs and stored in a parquet file. There are a few reasons as to why I did this:

First, when requesting data from their APIs, it requires the use of my personal API key tied to my Riot Games account. This key should not be shared with the public and would required some (potentially non-existant) method that I have not currently looked into to keep it hidden and the code still publicly accessible.

Second, this project uses player match histories to attempt to predit the outcome of the game. This dataset changes every time a request is made, making it diffcult to have reproducible results when working on the machine learning models.

Third, there is a limit to the amount of requests that can be made every minute so gathering the data for a larger dataset takes a long time. For example, the models in this project are trained on 500 matches, totalling over 500 requests, which takes over 10 minutes to accomplish.

More information on how the data was collected can be found in the following sections of LoL_Win_Predict_Big.ipynb:
1. Get user PUUID using their Riot ID and Tagline
2. Get user match history (past 50 games)
3. Get match information
4. Extract desired user stats for every match using their PUUID

The data used in LoL_Win_Predict_Static is available as used in my code (parquet.gzip) as well as a csv for quick-viewing in GitHub.

## Required Libraries
- pyarrow
- pandas
- seaborn
- matplotlib
- numpy
- sklearn
- scipy
- dtale (used but optional - easier DataFrame viewing in Jupyter Notebook)
