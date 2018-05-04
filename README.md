### Catch Probability - an ingredient for new defensive baseball statistics
#### A model (including home runs) based on bat speed and hit angle

![](https://i.imgur.com/homXGuA.png)

There are many statistics for batting and pitching, but there aren't many defensive statistics.  The primary reason is that batters and pitchers have a clear outcome for every baseball 'event' - was a strike or ball thrown, was a hit made and what base movement occured.  But in defensive statistics, one of the only metrics is the 'error' (which is a very low probability event - about 1.5% of all balls hit into play in 2017 resulted in an error).  Yet there seems a lot of variability in outcomes of what fly balls and line-drives are caught, but no good metric to measure this.

There has been great breakthroughs in thinking about this in the past 2 years due to improvements in Stacast data from the MLB.  The basic idea is that if you know the probability that a ball in flight is caught (catch probability), and you know where a player decides to position themself before a bat is hit into play, you could see if that player 'outperformed' other players over tens of thousands of hits in the same position catching the ball.   This is especially interesting for outfielders, who  have the most amount of 'hang time' to position themselves after a ball is hit.

My professor turned me on to the great power of Statcast data with this work, by suggesting I look at pybasell library.  Up to this point the class looked at traditional data sources (Lahman, Retrosheet and data recorded in FanGraphs).  pybaseball pulled some data from a site called  basebasesavant.mlb.com which contained a *very* interesting set of Statcast Data.

From that starting point began the journey to  understand 'catch probability' - which at its core can be predicted by three things:
1. Launch speed - the speed in mph that a ball leaves a batters bat (range is 0-125mph)
2. Launch angle - the angle the ball leaves the batters bat (+/- 70 degrees)
3. A data set of whether balls were caught with the same launch angle and launch speed.

This notebook outlines the activity to:

1. Acquire the raw data (using all balls hit into play in the 2017 season)
2. Inspect and validate the raw data
3. Augment dataset with new columns
4. Analyze augmented data set
5. Prove that the new statcast metrics of launch and and launch speed were statistically valid
6. Develop a model that forward predicts 'catch probability' base only on launch angle and hit speed
7. Demonstrate catch probability in an application (this notebook).

![](https://i.imgur.com/IoB8SHX.png)

![](https://i.imgur.com/3idix3k.png)

![](https://i.imgur.com/JRN1tTn.png)

![](https://i.imgur.com/UIxcmtR.png)

![](https://i.imgur.com/ebUpdrz.png)

Starting points:
- __[pybaseball](https://github.com/jldbc/pybaseball/blob/master/pybaseball/statcast.py)__
- statcast data available - scraped from [baseballsavant.mlb.com][https://baseballsavant.mlb.com/statcast_search]
- Catch probability - Statcast overview https://www.mlb.com/news/statcast-introduces-catch-probability-for-2017/c-217802340

Note: before this class I had been to a few baseball games, was a novice about baseball rules, knew NOTHING about baseball metrics/statistics. 


#### Credit
Screen scraping for batting data was leveraged from original pybaseball code