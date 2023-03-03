## Identify Archetypes among Genshin Impact Players

### Executive Summary

Using publicly avaiable game data among a sample of Genshin Impact Players, we obtained a four distinctive archetypes which their differences were largely driven by the number of active days in the game. From other variables, such as number of in-game achievements, number of characters and level of exploration, we were able to identify different levels of intensity for various in-game activities. With that, we named the four archetypes after the student classification names for the four undergraduate years - Freshman, Sophomore, Junior and Senior. For players who are able to relate to the archetypes, we have put forth some recommendations for them.

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

From our exploratory data analysis, we picked up some interesting findings:

If there would be one variable that seems to drive the prediction of other variable, then it would be the number of active days playing the game. The assumption is that if one plays the game more, the more likely it is to explore the maps, acquire more game characters and weapons. Exhibit 1 shows the distribution of Active Days. Although we did not achieved a good spread around 600-700 range, it did not have a significant impact on our further analysis using clustering analysis. Quite a lot of players have been playing over 800 days which means that they must have supported the game since launched. 

Exhibit 1: Distribution of Players by no. of Active Days<br>
<img src="/graphics/exhibit_1.jpg" width=50% height=50%></img>

The experience points needed to level up the Adventure Rank is non-linear (i.e. expoential), therefore it gets harder and harder to level up. The plotted trend line confirms this relationship. The fastest lvl 60 player from the data is about 500 days, which is about 1.5 years (Exhibit 2). 

Exhibit 2: Trend between Adventure Rank Level and no. of Active Days<br>
<img src="/graphics/exhibit_2.jpg" width=50% height=50%></img>

A similar trend is observed for in-game Achievements and notably, the spread is wide. In less than a year, there are few players who managed to complete more than 700 achievements (Exhibit 3).

Exhibit 3: Trend between No. of Achievements and no. of Active Days<br>
<img src="/graphics/exhibit_3.jpg" width=50% height=50%></img>

While it is likely that a player will have more characters with more Active Days, having more characters than expected in relationship with the number of Active Days would indicate that a player might have invested resources into the game. From Exhibit 4, we could observe a fairly wide spread away from the trend line.

Exhibit 4: Trend between No. of Characters and no. of Active Days<br>
<img src="/graphics/exhibit_4.jpg" width=50% height=50%></img>

As HoyoLab limits the number of characters showcase to 8, therefore sets the limit on the number of maximums 5-Star characters, This may not be the total number of 5-Star characters the player has. From this limitation, the maximum number of constellations in the showcase is 48. From Exhibit 5, we could see there are few players who have much more constellations than expected.

Exhibit 5: Trend between No. of Constellations among 5-Star Characters and no. of Active Days<br>
<img src="/graphics/exhibit_5.jpg" width=50% height=50%></img>

While there seems to be participation in setting up the Teapot in the game, a lot of players seems to stop at the 20,000 point mark, therefore reaching the minimal level to obtain a maximum reward in the game. This is an indication that a lot of players participate in the Teapot decoration just for the rewards and are less interested to go beyond. 

Exhibit 6: Trend between Teapot Comfort Score and no. of Active Days<br>
<img src="/graphics/exhibit_6.jpg" width=50% height=50%></img>

The Spiral Abyss Score is calculated based on the highest floor-chamber reached by the player (Max = 36 (12 floor with up to 3 chambers)). From Exhibit 7, we can observe that a fair number of players do not participate in the Spiral Abyss. Among those who reached the high floors (9 - 12) therefore with a score of at least 24, shows a good spread.

Exhibit 7: Trend between Spiral Abyss and no. of Active Days<br>
<img src="/graphics/exhibit_7.jpg" width=50% height=50%></img>

For the complete analysis, please refer to eda_and_analysis.jpynb found in the code folder.
_______
### Meet the Archetypes - Freshman, Sophomore, Junior and Senior

As we do not have categorical data in our dataset, therefore we could use one of the two popular methods, K-Means and Hierachical Clustering, to obtain the archetypes. The Hierachical Clustering did not produce a good result, therefore the K-Means clustering result was used instead. A 4-cluster solution was identified. We named the clusters as Freshman, Sophomore, Junior and Senior, after realising that the findings seems to suggest 4 stages of progression. 

We examined the values for each variable by archetypes and the differences are all statistically significant. In Exhibit 6, we observe that the archetypes tend to land comfortably in fairly distinctive ranges. Although some outliers can be observed from Freshman, we felt that the overall trend is evident.

Exhibit 8: Archetypes are failry distinctive based on Active Days<br>
<img src="/graphics/exhibit_8.jpg" width=50% height=50%></img>

The table below shows the inter-quatile range of the varirables according to each cluster. For the description of each variable, please refer to the Appendix below.


|Variables                             | Freshman  | Sophomore | Junior    | Senior    |
|:-------------------------------------|:---------:|:---------:|:---------:|:---------:|
|active days                           |  092-258  |  203-495  |  414-586  |  557-840  |
|level                                 |   45-55   |   55-58   |   57-60   |   59-60   |
|achievements                          |  240-406  |  394-628  |  628-872  |  750-875  |
|characters                            |   26-36   |   34-46   |   42-50   |   45-54   |
|5-star characters                     |    2-5    |    3-7    |    6-8    |    7-8    |
|constellation among 5-star characters |    0-1    |    0-3    |    1-5    |    1-9    |
|5-star weapons                        |    0-1    |    0-3    |    1-4    |    2-5    | 
|refinement among 5-star weapons       |    0-1    |    0-3    |    1-5    |    2-6    | 
|total exploration score               | 1890-3812 | 3596-6081 | 5781-6850 | 6577-6930 |
|oculi                                 |  168-355  |  332-542  |  492-613  |  562-613  |
|common chests                         |  313-776  | 0732-1637 | 1555-2213 | 2074-2385 |
|exquisite chests                      |  064-637  | 0582-1108 | 1129-1441 | 1472-1527 |
|precious chests                       |  097-198  |  183-339  |  330-442  |  411-468  |
|luxurious chests                      |   38-80   |  073-134  |  127-170  |  157-181  |
|remarkable chests                     |   03-26   |   20-84   |   71-134  |  113-145  |
|unlocked waypoints                    |  181-255  |  231-283  |  264-286  |  282-286  |
|unlocked domains                      |   28-39   |   36-46   |   43-48   |   46-48   |
|teapot visitors                       |    0-2    |    1-9    |    5-26   |   20-64   |
|teapot comfort score                  | 2940-5630 |10210-14990|20500-23510|30433-35425|
|teapot items                          |  099-293  |  422-862  | 0841-1721 | 1833-3027 |
|teapot realms                         |    1-1    |    2-4    |    4-5    |    5-5    |
|abyss score                           |   00-24   |    0-32   |   24-36   |   24-36   |

Note:<br>
The Spiral Abyss Score is calculated based on the highest floor-chamber reached by the player (Max = 36 (12 floor with up to 3 chambers))  
HoyoLab limits the showcase of maximum of 8 characters and 8 weapons, therefore the maximum no. of constellations and refinements are 48 and 40 respectively.

For the complete analysis, please refer to eda_and_analysis.jpynb found in the code folder.
_______
### Limitation of Study

On one hand, starting with the Discord Sample would ensure that we are gathering data from players who are currently active in the game, it is biased towards players who needs help or would like to help others. The low success rate adds further biaseness to the sample as there might be difference between players who made their data public and those who did not. While the resultant clusters seems logical and relatable, we are not confident that the sample is representative of Genshin Impact players, therefore the stated cluster size should be taken as indicative.
_______
### Conclusions and Recommendations

Based on the k-Means clustering, we obtained four distinctive archetypes that is largely based on the level of involvement in the game. The number of active days is a key variable that helps to make this definition while the rest of the variables provide an indication on typical intensity of various activiites. The Serenitea pot and Spiral Abyss are two side but they appeared to be more distinctive between the archetypes.

Anecdotally, we know that it is not uncommon for gamers to have more than one game account and the secondary accounts may fit into a different archetypes. While making our recommendations for each archtypes, we ocused on gamers with a single account.

#### 1. Freshman - you need not be alone

While Genshin Impact is not a complicated game, there are many useful tips that freshmen can pick up through social media and friends. Many started out watching Youtube or Twitch streamers or read online articles to pick up useful tips. One thing about Genshin Impact is that you could play this game entirely alone, therefore there isn't much pressure to know more people in order to progress in game. However, there are quite a few challenging content that might be easier if you pair up with experience gamers.

#### 2. Sophomore - becoming better at the game

You probably covered quite a lot of the easy content and probably has to face the tougher ones. This is the stage when you start to develop deeper understanding of the game mechanism, such as choosing artifacts and planning team composition. There is a lot of useful information resources that can help you but don't be shy to ask people for advice. Sometimes, it is better to learn from friends than online resources. In some discord servers, there might be specific channel that provide help to gamers. If you have not ventured into Spiral Abyss, it may be worthwhile to try it out. It takes a while to move up the floors, so don't be disappointed if you cannot clear everything in one go. 

#### 3. Juniors - move at your own pace

The distinction between Juniors and Seniors, beside number of active days, Seniors just have everything more and done more than Juniors. Perhaps you have come to terms with some of the achievements which are rather painful (e.g. fishing and growing crops in the teapot), you have decided to finish it or give it up totally. There is proably no hurry to rush them through unless you really want those free primogems. You probably want to take your time to venture the remainding content, otherwise, you might end up like the Seniors with very little left to do.

#### 4. Seniors - finding meaning to continue - what's next?

Senior have been supporting the game and have played out most, if not all the content that is available. They are up to date with the latest content and hungry for me. Probably at some time, or already so, you might stop for a while or slow down, or perhaps find that friends whom have been playing the game no longer do so. There is probably a time when you might move on with the game and do something else. The main point is that you have enjoyed the game and have many happy moments, and if you continue to do so, may you have many more happy memories in the future. When there is free time, Seniors are excellent in helping others in challenging content. 

_______
## Appendix
### File Management

| Folder        | Description                                                                                             |
|:--------------|:--------------------------------------------------------------------------------------------------------|
| codes         | Contains the python codes used in the analysis (1) data_collection.jpynb and (2) eda_and_analysis.jpynb |
| data          | Contains the deidentified data used in this project                                                     |
| data_setup    | Contains details on the data conversion from pydantic to dataframe                                      |
| presentation  | Contains the presentation slides for the project                                                        |
| graphics      | Contains the chart jpg files in the README                                                              |

### Dsecription of the Data Fields in the Dataset
|Data Fields          | Description                                                                                             |
|:--------------------|:--------------------------------------------------------------------------------------------------------|
|days_active          | no. of active days playing the game (current game max  > 860)                                           |
|level                | current adventure rank level of the player (current game max = 60)                                      |
|achievements         | no. of game achievements (current game max  = 890)                                                      |
|characters           | no. of characters the player has (current game max  = 63)                                               |
|total_5_characters   | no. of 5-star characters showcased in the public profile (data limitation max = 8)                      |
|total_5_constellation| no. of constellations among 5-star characters showcased in the public profile (data limitation max = 48)|
|total_5_weapon       | no. of 5-star weapons showcased in the public profile (data limitation max = 8)                         |
|total_5_refinement   | no. of refinement among 5-star weapons showcased in the public profile (data limitation max = 40)       |
|total_explored       | combined total exploration score of all the maps that were available (current game max = 7,000)         |
|culi                 | no. of oculi collected (e.g. anemoculus) (current game max = 613)                                       |
|common_chests        | no. of common chests opened                                                                             |
|exquisite_chests     | no. of exquisite chests opened                                                                          |
|precious_chests      | no. of precious chests opened                                                                           |
|luxurious_chests     | no. of luxurious chests opened                                                                          |
|remarkable_chests    | no. of remakable chests opened                                                                          | 
|unlocked_waypoints   | no. of unlocked waypoints                                                                               |
|unlocked_domains     | no. of unlocked domains                                                                                 |
|teapot_level         | level of the serenitea pot (current game max = 10)                                                      |
|teapot_visitors      | total no. of visitors received in serenitea pot                                                         |
|teapot_comfort       | highest comfort score of the sernitea pot among the available realms                                    |
|teapot_items         | no. of items made in Serenitea Pot                                                                      |
|teapot_realm         | no. of realm unlocked in Serenitea Pot (current game max = 5)                                           |
|abyss_score1         | converted score based on th highlight level of spiral abyss reached (max = 36 (12 floor x 3 chambers))  |
|abyss_score2         | converted score based on th highlight level of spiral abyss reached (max = 12 (floor 9-12 x 3 chambers))|

Note:<br>
As we can only collect the data in batches and not all at the same time, noted that active players would have new updated figures almost on a daily basis. teapot_level and abyss_score2 were not used in the clustering as they are closely related to other variables.
