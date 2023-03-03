## Identify Archetypes among Genshin Impact Players

### Executive Summary

TBA

_______
### Problem Statement

Determine what are the different archetypes using publicly available game data with the aim to help Genshin Impact players know more about themselves and the community. Where possible, the findings could provide some suggestions or tips to gthe players based on the archetype they belong to.
_______
### Background

Gaming companies potentially have a lot of user data that can help them to understand their players better. One way is to use the marketing segmentation approach to identify distinct groups of customers. In doing os, it is possible to develop customised strategies for different segments. A similar concept is used in user research which aims to identify different archetypes so that they can customised their user journey. For games that are based on free-to-play (F2P), they usually have microtransactions for players to spend real money on game assets. For these games, it is quite intuitive to segment the players based profitability. Games which have been around for a longer time might group gamers into new, lapsed and active gamers, as the first step to ensure the longevity of the game. This project takes the perspective of the gamers, to identify different archetypes based publicly avaiable data, so that it could be an interesting discovery which archetype they belong to.

#### 1. About the game

Genshin Impact is an anime-style action role-playing game developed and published by MiHoYo (now named as HoyoVerse). It was released for Android, iOS, PlayStation 4, and Windows in 2020, on PlayStation 5 in 2021. Now in its third year of running, it has already earned earned $4 billion [(Source: Sportskeeda)](https://www.sportskeeda.com/esports/news-genshin-impact-among-successful-mobile-games-ever-earned-4-billion-2023#:~:text=According%20to%20Sensor%20Tower's%20latest,%241.4%20billion%20came%20from%20ChinaGenshin) Similar to other successful and profitable mobile games, Genshin Impact is a Free-to-Play (F2P) title with the option for players to spend money on game assets.

#### 2. Other Public Information on Players' Profile

Perhaps this might came as a surprise, the profile of Genshin Impact players seems to be much older than expected. According to an article by udonis dated 9 Feb 2023, 27% of players are under 25, while the average age is 35. There might be a possibility that the game account of a young player might be registered through their parents' mobile account. From the same source, it also stated that 
- 30% of players only play once a day, 14% do it twice, and 13% play at least 9-14 times a day
- 7% of players play an average of 3-10 minutes per session, while 26% play for at least 10-30 minutes and 23% playing between 1 and 10 hours per day

[(Source: udonis)](https://www.blog.udonis.co/mobile-marketing/mobile-games/genshin-impact-advertising#:~:text=Genshin%20Impact%20Demographics&text=The%20gender%20distribution%20is%20quite,the%20average%20age%20is%2035) 
_______
### Data Source and Sampling

HoYoLAB is the gaming community forum for HoYoverse games which registered users can share some of their user data with others. To obtain these user data, we made use of [genshin.py](https://pypi.org/project/genshin), which was developed by Genshin Impact fans. A successful retrieval involved crossing two hurdles - (i) the player is a registered user in HoyLAB and (ii) has made the player data public. We have attempted to use random number generation to get user data but the success rate is very low (i.ei. <5%). We ended up looking into chat channels in popular Discord servers where players disclose their User ID (UID) so that they can seek help from other players for game challenges. We gathered UID from the Asia, North America (NA) and Europe (EU) servers for the month of Janurary 2023 and parse them into genshin.py in batches over a period from Janurary to mid-Feburary 2023. The success rate is about 14-16% by server. 

With this, we obtained a sample of 1,203 user data with a success rate of about 14-16% per server (i.e. Asia, NA and EU). we did not observe any significant difference in the user data by servers using one-way Anova test, therefore we decided to put the data together for the analysis. 

For confidentiality, the UID in the data is replaced by a running ordered index so that the users are de-identified.
_______
### Exploratory Data Analysis

If there would be one variable that might predict the other variable, it would be the number of active days in the game. The assumption is that if one plays the game longer, is more likely to complete more exploration and get more game characters and weapons. We did not achieved a good spread around 600-700 range while quite a lot of players have been playing over 800 days. These 800+days players must have supported the game since its start. 

Exhibit 1: Distribution of Players by no. of Active Days<br>
<img src="/graphics/exhibit_1.jpg" width=50% height=50%></img>

Genshin Impact players can relate that its requires more and more experience points to level up Adventure Rank, therefore it is a non-linear relationship (e.g. expoential). The fastest lvl 60 player from the data is about 500 days, which is about 1.5 years. 

Exhibit 2: Trend between Adventure Rank Level and no. of Active Days<br>
<img src="/graphics/exhibit_2.jpg" width=50% height=50%></img>

Exhibit 3: Trend between No. of Achievements and no. of Active Days<br>
<img src="/graphics/exhibit_3.jpg" width=50% height=50%></img>

Exhibit 4: Trend between No. of Characters and no. of Active Days<br>
<img src="/graphics/exhibit_4.jpg" width=50% height=50%></img>

|Data Fields          | Description                                                                                                 |
|---------------------|-------------------------------------------------------------------------------------------------------------|
|days_active          | The no. of active days playing the game (Current Game Max  > 860)                                           |
|level                | The current adventure rank level of the player (Current Game Max = 60)                                      |
|achievements         | The no. of game achievements (Current Game Max  = 890)                                                      |
|characters           | The no. of characters  the player has Current Game Max  = 63)                                               |
|total_5_characters   | The no. of 5-star characters showcased in the public profile (Data limitation Max = 8)                      |
|total_5_constellation| The no. of constellations among 5-star characters showcased in the public profile (Data limitation Max = 48)|
|total_5_weapon       | The no. of 5-star weapons showcased in the public profile (Data limitation Max = 8)                         |
|total_5_refinement   | The no. of refinement among 5-star weapons showcased in the public profile (Data limitation Max = 40)       |
|total_explored       | A combined exploration score of all the maps that were available (Current Game Max = 7,000)                 |
|culi                 | The total no. of Oculi collected (e.g. Anemoculus) (Current Game Max = 613)                                 |
|common_chests        | Total no. of common chests opened                                                                           |
|exquisite_chests     | Total no. of exquisite chests opened                                                                        |
|precious_chests      | Total no. of precious chests opened                                                                         |
|luxurious_chests     | Total no. of luxurious chests opened                                                                        |
|remarkable_chests    | Total no. of remakable chests opened                                                                        |
|unlocked_waypoints   | Total no. of unlocked waypoints                                                                             |
|unlocked_domains     | Total no. of unlocked domains                                                                               |
|teapot_level         | Level of the Serenitea Pot(Current Game Max = 10)                                                           |
|teapot_visitors      | Total no. of visitors received in Serenitea Pot                                                             |
|teapot_comfort       | The highest comfort score of the Sernitea Pot among the available realms                                    |
|teapot_items         | Total no. of items made in Serenitea Pot                                                                    |
|teapot_realm         | Total no. of realm unlocked in Serenitea Pot (Current Game Max = 5)                                         |
|abyss_score1         | The converted score based on th highlight level of Abyss Reached (Max = 36 (12 floor x 3 chambers))         |
|abyss_score2         | The converted score based on th highlight level of Abyss Reached (Max = 12 (floor 9-12 x 3 chambers))       |

Note:
As we can only collect the data in batches and not all at the same time, noted that active players would have new updated figures almost on a daily basis. teapot_level and abyss_score2 were not used in the clustering as they are closely related to other variables.
_______
### Applied Clustering

As we have avoided categorical data, therefore we could use one of the two popular methods, K-Means and Hierachical Clustering, to obtain the archetypes. The Hierachical Clustering did not produce a good result, therefore the K-Means clustering result was used instead. A 4-cluster solution was identified.
_______
### Summary of Findings
_______
### Limitation of Study

On one hand, starting with the Discord Sample would ensure that we are gathering data from players who are currently active in the game, it is biased towards players who needs help or would like to help others. The low success rate adds further biaseness to the sample as there might be difference between players who made their data public and those who did not. While the resultant clusters seems logical and relatable, we are not confident that the sample is representative of Genshin Impact players, therefore the stated cluster size should be taken as indicative.
_______
### Conclusions and Recommendations

_______
## Appendix
### File Management

| Folder        | Description   |
| ------------- | ------------- |
| codes         | Contains the python codes used in the analysis (1) data_collection.jpynb and (2) eda_and_analysis.jpynb |
| data          | Contains the deidentified data used in this project |
| data_setup    | Contains details on the data conversion from pydantic to dataframe |
| presentatione | Contains the presentation slides for the project |
