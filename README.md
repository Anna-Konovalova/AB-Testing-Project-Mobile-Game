# A/B Testing Project 

Mobile Game - Cookie Cats
======

Project Overview
------
<img width="798" alt="game_cover_pic" src="https://user-images.githubusercontent.com/78367070/203767538-f0af4589-a859-4a03-b783-bf49bdd05b0b.png">

[Cookie cats](https://www.facebook.com/cookiecatsgame) is a hugely popular mobile puzzle game developed by [Tactile Entertainment](https://tactilegames.com/). It's a classic "connect three"-style puzzle game where the player must connect tiles of the same color to clear the board and win the level.

<img width="813" alt="Image_1" src="https://user-images.githubusercontent.com/78367070/203767725-144cb5dc-8ae4-463a-828d-01edb0000baf.png">

As players progress through the levels of the game, they will occasionally encounter gates that force them to wait a non-trivial amount of time or make an in-app purchase to progress. In addition to driving in-app purchases, these gates serve the important purpose of giving players an enforced break from playing the game, hopefully resulting in that the player's enjoyment of the game being increased and prolonged.

But where should the gates be placed? Initially the first gate was placed at level 30, but in this project I analyse an A/B test where the first gate in Cookie Cats was moved from level 30 to level 40. In particular, I look at the impact on player retention.


Tech
------
This Project was completed in Python. For data manipulation I used Pandas and NumPy. For data visualisation I used Matplotlib and Seaborn. 


Data
------
The dataset for this project is *cookie_cats.csv*.

The data is from 90,189 players that installed the game while the A/B test was running. The variables are:

**userid** - a unique number that identifies each player. <br>
**version** - whether the player was put in the control group (gate_30 - a gate at level 30) or the group with the moved gate (gate_40 - a gate at level 40). <br>
**sum_gamerounds** - the number of game rounds played by the player during the first 14 days after install. <br>
**retention_1** - did the player come back and play 1 day after installing? <br>
**retention_7** - did the player come back and play 7 days after installing? <br>

When a player installed the game, he or she was randomly assigned to either gate_30 or gate_40.


Project Workflow
------
In this project, I completed the following steps (these steps are described in detail in *Mobile_Game_AB_Testing.ipynb*.
1. Checking that each A/B group has approx. the same number of players
2. Looking at the distributions of game rounds
3. Looking at the overall 1-day retention
   A common metric in the video gaming industry for how fun and engaging a game is 1-day retention: the percentage of players that comes back and plays the game one day after they have installed it. The higher 1-day retention is, the easier it is to retain players and build a large player base.
4. Bootstrap analysis for 1-day retention 
5. Checking probability of the estimated difference for 1-day retention
6. Looking at the overall 1-day retention
7. Bootstrap analysis for 7-day retention
8. Checking probability of the estimated difference for 7-day retention
9. Conclusion


Project Summary
------
The bootstrap result shows that there is strong evidence that 7-day retention is higher when the gate is at level 30 than when it is at level 40. The conclusion is: in order to keep retention high — both 1-day and 7-day retention — the gate should not be moved from level 30 to level 40.

Other metrics could be looked at as well, like the number of game rounds played or how much in-game purchases are made by the two A/B-groups. But retention is one of the most important metrics. If player base is not retained, it doesn't matter how much money they spend in-game.

So, why is retention higher when the gate is positioned earlier? One could expect the opposite: the later the obstacle, the longer people are going to engage with the game. But this is not what the data tells us. The theory of **hedonic adaptation** can give one explanation for this. In short, hedonic adaptation is the tendency for people to get less and less enjoyment out of a fun activity over time if that activity is undertaken continuously. By forcing players to take a break when they reach a gate, their enjoyment of the game is prolonged. But when the gate is moved to level 40, fewer players make it far enough, and they are more likely to quit the game because they simply got bored of it.
