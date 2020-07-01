# NBA Player Position Statistic Analysis
In this repository, I have shown the position Statistic Analysis of Several NBA Players

# Who is the best/worst NBA player, per draft position?
Best/worst player is mainly about opinion and preference, and stats cannot simply justified the best/worst argument as basketball and sports in overall cannot be judged only by stats and number, so it's a controversial topic.

Who doesn't know what a draft is, it is a method for NBA teams to "recruit" new players from colleges or overseas. The recruitment process happened sequentially, so the team that get the first pick can recruit player first, and so on. With such method, it is expected that the first player drafted is the best player from the recruitment class. But sometimes, we got a highly picked player that doesn't meet the expectation or a lowly drafted player that overcome the expectation. Using this dataset, I will try to analyze which player that actually over/underacieved their draft position.


## Kobe Bryant's average points per season
![kobe](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/kobeavgpoint.png)


## Bruce Bowen's average points per season
![bruce](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/bruceavgpoint.png)


### Complete Data Stats
![detail](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/detail.png)

Here we got some descriptive statistics of numerical features. We can see that the dataset contain many single game appearence. While this not really affect many of the essential stats (points, assists, rebounds, etc.), single game appearence really disturb the net rating. For example, the max net rating recorded in the dataset is 300 while the lowest is -200. This is happens because in one of those single game appearence, that player maybe only played in garbage time thus the net rating deflated.

To deal with this, we can use three approaches: drop the record of player who only played few number of games for every season, drop the record of player who only averaged few number of games overall, or simply removed this features from consideration. All of this approaches have their own pros and cons. In the first approach, we can drop some record of a player who actually has a decent career, but has one or two seasons with only one appearances due to injury/rough start. For example, I have shown the career of Kobe Bryan.

Here we can see that Kobe start his first NBA season by only played one game with deflated net rating of 300, but after that he definitely has a legendary career with the San Antonio Spurs. If we choose the first approach, we will neglect his career start, but we can slightly alter his points per game for example, and can create some bias. If we choose the second approach, we will keep this deflated stats and affect our calculation. The third approach is more neutral, but I want to keep it as it can differentiate good player in good team or bad team. 

To decide my approach, I wanted to know how many records that contain gp point=1 and Net rating is more than 20. There are many similar cases in the dataset. Therefore, my approach is to discard player who average less than 3 games for their entire career when we rank the players.

### Then as we want to measure per draft number, we want to know how many draft class are there in the dataset
![draft](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/2000to17.png)

### let's see the trend of traditional stats regression plot (points, assists, rebounds) against the draft position

![ptsdraft](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/pointdraftreg.png)
![astdraft](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/astdraftreg.png)
![rebdraft](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/rebdraftreg.png)
![avgdraft](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/avgdraft.png)

It's seems that the overall trend shows that higher draft pick gives better number. But let's see the the actual number as we can see many outliers in the graph.

We found out two names that create the spike at gp: Manu Ginobili and Isaiah Thomas. IT create the spike in ppg due to his inprobable all-star form in Boston Celtics and Manu just being Manu. Seeing the downhill of IT is a sad story though.

### Manu Ginobili
![manu](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/manu.png)

### Isaiah Thomas
![thomas](https://github.com/swarnajyoti/NBA_PlayerPosition_StatAnalysis/blob/master/Images/thomas.png)


## Best player for each draft pick
Here's the complete list of best player for each draft pick, measured by the 'score' metrics. We'll see some of great players that we expect is the best on his draft position. Now I want to mention some interesting results.

1. First, the 'OKC trio' actually was the best 2nd, 3rd, and 4th draft pick since 1995 and all of them have become league MVP. With the addition of Steven Adams (12th pick) and Serge Ibaka (24th pick), OKC drafted 5 players that become the best in their pick (CMIIW). OKC scouts really have good eyes on sleeper player.

2. GSW drafted 3 players (Steph, Klay, and Draymond) that are the best in their respective draft pick position.

3. As we expect, Bruce Bowen has the highest 'score' due to his inflated net rating. If we not consider him, Nikola Jokic has the highest 'score', thus the most overachieve player since 1995.

4. The 59th pick does not give any sleeper players so far. The best of 59th pick is DJ Strawberry with a score of 7.6.

5. In the case of 8th pick, the best player is Andre Miller. Among the top 10 pick, only 8th pick that actually has a non all-star player as their best player. But it is reasonable as beside Miller, other notable players are KCP, Rudy Gay, and Jamal Crawford.


### Interestingly one of questionable result: where is Kobe Bryant? Instead of Kobe, the best player in 13th pick is Donovan Mitchell. This is happened most likely because: Mitchell average more games per season and has higher net rating than Kobe. In his old days, Kobe suffer many harsh injuries and mediocre teammate that affect his total stats.

# Conclusion
We have see the best/worst NBA player per their draft position and analyze why the results happened. Well it is not the most objective results, as we use many assumption for our analysis. We also only use a simple metric to rank the players. For the future, I want to use more advanced machine learning method to classify players 'tier', which also become one of the most debatable topic among NBA fans. I welcome any suggestion about my method/analysis. Cheers!
