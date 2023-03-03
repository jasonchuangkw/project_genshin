## Applied Clustering to Genshin Impact Data to Identify Archetypes

### Executive Summary

TBA

_______
### Problem Statement

Determine what are the different archetypes based on public game data that could help the Genshin Impact plauyers know more about themselves and the community. Where possible, the findings could provide some suggestions or tips to gthe players based on the archetype they belong to.

_______
### Background

Gaming companies potentially have a lot of user data that can help them to understand their players better. One method is to adopt the marketing segmentation approach by having customised strategies for different archetypes. For games that are based on free-to-play (F2P) which have microtransactions for players to spend real money on game assets, it is quite typical to segment players based on their profitability. Games which have been around for a longer time might look at new gamers, lapsed gamers and existing active gamers. This project takes the perspective of gamers to identify different archetypes based publicly avaiable data, so that it will be useful to players to understand how involved they are in the game as compared to others.

#### 1. About the game

Genshin Impact is an anime-style action role-playing game developed and published by MiHoYo (now named as HoyoVerse). It was released for Android, iOS, PlayStation 4, and Windows in 2020, on PlayStation 5 in 2021. Now in its third year of running, it has already earned earned $4 billion [(Source: Sportskeeda)](https://www.sportskeeda.com/esports/news-genshin-impact-among-successful-mobile-games-ever-earned-4-billion-2023#:~:text=According%20to%20Sensor%20Tower's%20latest,%241.4%20billion%20came%20from%20ChinaGenshin) Similar to other successful and profitable mobile games, Genshin Impact is a Free-to-Play (F2P) title with the option for players to spend money on game assets.

#### 2. Other Public Information on Players' Profile

It is interesting to note that the profile of Genshin Impact players is not limited to a young audience. According to an article by udonis dated 9 Feb 2023, 27% of players are under 25, while the average age is 35. There might be a possibility that the game account of a young player might be registered through their parents' mobile account. From the same source, it also stated that 
- 30% of players only play once a day, 14% do it twice, and 13% play at least 9-14 times a day
- 7% of players play an average of 3-10 minutes per session, while 26% play for at least 10-30 minutes and 23% playing between 1 and 10 hours per day

[(Source: udonis)](https://www.blog.udonis.co/mobile-marketing/mobile-games/genshin-impact-advertising#:~:text=Genshin%20Impact%20Demographics&text=The%20gender%20distribution%20is%20quite,the%20average%20age%20is%2035) 
_______
### Data Source and Sampling

HoYoLAB is the gaming community forum for HoYoverse games which registered users can make a selection of their user data public. To obtain these user data, we made use of [genshin.py](https://pypi.org/project/genshin), which was developed by Genshin Impact fans. A successful retrieval involved crossing two hurdles - (i) the player is a registered user in HoyLAB and (ii) has made the player data public. We have attempted to use random number generation to get user data but the success rate is very low (i.ei. <5%). We ended up looking into chat channels in popular Discord servers where  
players can seek help from other players for game challenges. With this, we obtained a sample of xxxx User ID for the month of January 2023. The User ID collected is limited to players from Asia, North America (NA) and Europe (EU) servers.

Parsing the Discord Sample of User ID into genshin.py, we collected XXXX data over a period from January to mid-Feburary with a success rate of 14-16% by server. Using one-way Anova test, we did not observe any significant difference in the user data by servers.

For confidentiality, the UID in the data is replaced by a running ordered index, therefore is deidentified from the users.

### Exploratory Data Analysis


### Applied Clustering

Since the fields in the data are numerical data, therefore we could use one of the two popular methods, K-Means and Hierachical Clustering, to obtain the archetypes. The Hierachical Clustering did not produce a good resul, therefore the final model made use of K-Means clustering using a 4-cluster solution.

### Summary of Findings

### Limitation of Study

On one hand, starting with the Discord Sample would ensure that we are gathering data from players who are currently active in the game, it is biased towards players who needs help or would like to help others. The low success rate adds further biaseness to the sample as there might be difference between players who made their data public and those who did not. While the resultant clusters seems logical and relatable, we are not confident that the sample is representative of Genshin Impact players, therefore the stated cluster size should be taken as indicative.

We attempted to use random number generation 


### Conclusions and Recommendations


## Appendix
### File Management

| Folder        | Description   |
| ------------- | ------------- |
| codes         | Contains the python codes used in the analysis (1) data_collection.jpynb and (2) eda_ana_analysis.jpynb |
| data          | Contains the deidentified data used in this project |
| data_setup    | Content code conversion used to prepare the data |
| presentatione | Contains the presentation slides for the project |
