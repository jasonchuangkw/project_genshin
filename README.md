### Applied Clustering to Genshin Impact Data to Identify Archetypes

#### Executive Summary

TBA

#### Problem Statement

Determine what are the different archetypes based on public game data that could help the Genshin Impact plauyers know more about themselves and the community. Where possible, the findings could provide some suggestions or tips to gthe players based on the archetype they belong to.

#### Background

Gaming companies potentially have a lot of user data that can help them to understand their players better. One method is to adopt the marketing segmentation approach by having customised strategies for different archetypes. For games that are based on free-to-play (F2P) which have microtransactions for players to spend real money on game assets, it is quite typical to segment players based on their profitability. Games which have been around for a longer time might look at new gamers, lapsed gamers and existing active gamers. This project takes the perspective of gamers to identify different archetypes based publicly avaiable data, so that it will be useful to players to understand how involved they are in the game as compared to others.

##### 1. About the game

Genshin Impact is an anime-style action role-playing game developed and published by MiHoYo (now named as HoyoVerse). It was released for Android, iOS, PlayStation 4, and Windows in 2020, on PlayStation 5 in 2021. Now in its third year of running, it has already earned earned $4 billion [(Source: Sportskeeda)](https://www.sportskeeda.com/esports/news-genshin-impact-among-successful-mobile-games-ever-earned-4-billion-2023#:~:text=According%20to%20Sensor%20Tower's%20latest,%241.4%20billion%20came%20from%20ChinaGenshin) Similar to other successful and profitable mobile games, Genshin Impact is a Free-to-Play (F2P) title with the option for players to spend money on game assets.

##### 2. Other Public Information on Players' Profile

It is interesting to note that the profile of Genshin Impact players is not limited to a young audience. According to an article by udonis dated 9 Feb 2023, 27% of players are under 25, while the average age is 35. There might be a possibility that the game account of a young player might be registered through their parents' mobile account. From the same source, it also stated that 
- 30% of players only play once a day, 14% do it twice, and 13% play at least 9-14 times a day
- 7% of players play an average of 3-10 minutes per session, while 26% play for at least 10-30 minutes and 23% playing between 1 and 10 hours per day
[(Source: udonis)](https://www.blog.udonis.co/mobile-marketing/mobile-games/genshin-impact-advertising#:~:text=Genshin%20Impact%20Demographics&text=The%20gender%20distribution%20is%20quite,the%20average%20age%20is%2035) 

#### Data Source and Sampling

HoYoLAB is the gaming community forum for HoYoverse games which registered users can make a selection of their player data public. To obtain these public data, we made use of [genshin.py](https://pypi.org/project/genshin), which was developed by Genshin Impact fans. A successful data collection has two hurdles - (i) the player is a registered user in HoyLAB and (ii) has made the player data public. We have attempted to use random number generation to get player data but the success rate is very low (i.ei. <10%). We ended up looking into chat channels in popular Discord servers where  
Genshin Impact players can seek help from other players for in game challenges. With this, we obtained xxxx number of User ID for the month of January 2023.

Using the Discord Sample, we collected XXXX data over a period from January to mid-Feburary, limiting to players from Asia, North America (NA) and Europe (EU) servers only. The success rate is about 14-16% by server. Using one-way Anova test, we did not observe significant difference in the variables by servers.

For confidentiality, the final data does not contain any User ID.

#### Analysis

Since the fields in the data are numerical data, therefore we could use one of the two popular methods, K-Means and Hierachical Clustering, to obtain the archetypes. The Hierachical Clustering did not produce a good resul, therefore the final model made use of K-Means clustering using a 4-cluster solution.

#### Summary of Findings

#### Limitation of Study

We attempted to use random number generation 


#### Conclusions and Recommendations
