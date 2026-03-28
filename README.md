# Galatasaray - Exploratory Data Analysis
Onat Safak

Galatasaray is the most successful team in Turkish football, with 25 titles earned in the Turkish Super Lig. More importantly, it is the team I have really deeply in my heart, as a proud fan for 15 years. Galatasaray’s success took a different path in the last 15 years, as they earned 8 of the 14 titles. This year, they are the leaders again, going to their 9th title in 15 years.

This data analysis project hopes to find trends leading to Galatasaray’s success. Firstly, general statistics about the club will be looked at over the seasons. Then, more specific factors like home advantage, derby performance, player performance, correlations of statistics, and finishing performance. The data is pulled from a sports statistics provider named API-Football. The data set has a total of 534 different games and 638 different player/season records.  Three separate endpoints were called: /fixtures for match results (16 API calls, one per season), /fixtures/statistics for per-match stats like possession, shots, and fouls (534 calls, one per fixture), and /players for seasonal player data. All responses were parsed from JSON into pandas DataFrames and saved to CSV for reproducibility.

Table 1 gives us an overview of the performance of Galatasaray across the seasons. It shows us, excluding the 21-22 season, that the goal difference is positive, and the team is usually expected to win. 

Graph 1 provides a visual representation of the points collected and win percentages for these seasons. Win percentage dips below 50% for the 15-16 and 21-22 seasons only. And this graph shows that the last 4 championships were significant successes, as it was a clear jump in the points and win percentages of the other seasons. It is important to note that looking at the final points themselves is not enough, since after the pandemic and the 2023 Earthquake in Turkey, the teams and matches played per season have been unstable. 

Graph 2 shows goals scored vs conceded per season. This is also consistent with Graph 1 findings. The 2021-2022 season was a significant failure for Galatasaray with a negative goal differential, and the last 4 seasons show that the scored goals are 2-4 times more than conceded.

Graph 3 shows the outcomes per season, which is an important addition to Graph 1 that does not hold draw or loss percentages. 

The first important analysis is whether playing at home provides Galatasaray with a significant advantage. Galatasaray is famous worldwide for its fans and incredible home atmosphere, its stadium being titled ‘The Hell’. So one of the questions I want to answer is whether the home advantage is real or how significant it is. After grouping games by home or away games, several statistics were analyzed.

Graph 4 compares the win rates, points per game, and average goals scored for home and away games, with home games having more in all three categories. 

Graph 5 is a horizontal bar chart showing more detailed statistics like fouls, corners, shots on target, shots, and possession. These are important metrics to understand how dominant a team is in the game, regardless of the score. Again, home games have higher averages per match in all of these metrics. This is suggestive that home advantage might be significant, but it is not enough to conclude. That is why the next step is a hypothesis test. 

Table 2 is a summary table for the t-test conducted for several variables. With an alpha of 1%, points, goals, shots, shots on target, possession, and corners are all statistically significant, while fouls are not. This shows us that the home advantage of Galatasaray is real. The team is significantly more dominant and successful in Rams Park than away. 

The next thing to look at is how Galatasaray is performing against its 3 biggest competitors in the league: Fenerbahce, Besiktas, and Trabzonspor. 

Table 3 is a summary table for the games against these 3 clubs. 

Graph 6 shows the head-to-head performance in derbies. It is important to realize that against Fenerbahce, draws are the most common result. This is an unusual thing, especially considering how rare draws were in Graph 3. 

Graph 7 shows the goals scored and conceded in these games. We see that Galatasaray scored more than it conceded against all these 3 rivals, even Fenerbahce, against whom it has the same win and loss numbers. Goals scored and conceded against Fenerbahce are significantly less than those against Besiktas and Trabzonspor, with 31 scored and 27 conceded in 32 games. This shows that teams are taking fewer risks against what is considered the biggest game in Turkish Football, eventually leading it to be a drier game with an average of fewer than 1 goals for each team. 

One more category looked at in detail was specific player performances. Graph 8 shows the top 15 goal contributors (goal+assist), with Burak Yilmaz leading and Icardi following. It is important to note that both are associated with two really successful times of the team in the last 15 years.

Graph 9 is a scatterplot that shows the minutes played on the x-axis and goals on the y-axis. Note that this is seasonal, and not overall for the Galatasaray career. The dots are color-coded based on rating. One finding is that as the minutes played increase, the rating increases, as the dots get noticeably green moving right, and most of the orange and reds are concentrated on the left, with a few minutes played. This shows that as players get more chances, they start to play better, and as they play better, they get more chances.

Graph 10 shows the top 20 players by rating and their average rating per season. It is an important indicator to show who is behind Galatasaray’s success.

Graph 11 looks at players by position. It was predictable that forwards and attackers would contribute the most, but I was surprised by how many midfielders scored goals from really close to the attackers and forwards. Also interesting to note that the total goals for goalkeepers is nonzero, as Fernando Muslera scored once in his first and once in his last seasons at Galatasaray. 

Graph 12 explores the minutes of the goals. Two meaks are around 45 and 90, the ends of the halves. This is possibly because goals scored at the extra times are recorded in the 45th and 90th minutes, overcounting those. Another notable thing is that both halves start slowly, with fewer goals scored compared to the rest of the game.

Graph 13 is the correlation matrix between several statistics. This provides some really important findings. Some really high correlations are obvious and predictable, like the high positive correlations between goal difference and points, goals and points, shots and shots on target, shots on target and goals, etc. It is also predictable that points and opponent goals, and goal difference and opponent goals, would be highly negatively correlated. 

Some interesting findings from the correlation matrix is the negative correlations of Galatasaray fouls and yellow cards with the ‘good metrics’ like goals, shots, possession, etc. This suggests that under pressure, Galatasaray tends to play more aggressively, having more fouls and yellow cards. 

One other really interesting finding is what is not actually important for success. The correlation between corners and points is 0.05, and between possession and fouls is 0.04. This shows that even though we deem possession and corner as important metrics of dominance and strength of play, they are not causes of points. 

Graph 14 shows box plots for Wins, Draws, and Losses for shots, possession, and corners. The outcomes are consistent with the outcomes of graph 13. Shots are significantly higher for wins than for draws, which is more than for losses. Possession percentage is mostly consistent for different results, with medians around the high 50s. Median corners are slightly higher for wins, but this doesn't create much difference. 

Table 4 looks at the halftime scores vs final scores. Graph 15 visualizes the outcomes of Table 4. The finding of Graph 15 is that Galatasaray is way more likely to turn around a loss than give away a win. The win percentage for games with halftime winning is around than 90%, while the loss percentage for games with losing first halves is less than 50%.

The final thing looked at in this project was the final stretch performance. Galatasaray is also known for its “fifth gear,” which starts to operate when a championship is near. I wanted to see if that was a myth or if an actual difference in performance was visible. 

Table 5 looks at the last 10 game performances against the rest of the season, for years Galatasaray finished as champions and not. Graph 15 visualizes the findings. For years, Galatasaray has been a champion, with point average increases in the last 10 games, and for seasons they are not, it decreases significantly in the last 10 games. This suggests that the final power of Galatasaray is actually real. In seasons they are in the title race, they start performing better, and in the years they are not in the title race, they actually start performing worse, probably due to morale. 

This analysis of 534 Galatasaray matches and 638 player-season records across fifteen Süper Lig seasons revealed several clear patterns. Galatasaray's recent dominance is not gradual, as the last four championship seasons represent a visible jump in points and win rate compared to the rest of the decade. The home advantage at Rams Park is statistically significant, indicating that home advantage is a really important factor in Galatasaray’s success.

Derby games suggest that while Galatasaray has a positive goal differential against all 3 rivals, Fenerbahce games are extremely cautious with few goals and points. Looking at correlation led to some counterintuitive findings indicating that some football theories might be wrong: possession and corners are unrelated to the team’s success. What actually predicts success is shots on target and goal difference, indicating that finishing quality matters far more than control.

The halftime analysis showed that Galatasaray protects leads exceptionally well and is more likely to recover from a deficit than to collapse from a winning position. Finally, the final stretch analysis confirmed what Galatasaray fans call the "fifth gear" or “owning the Mays”: in championship seasons, the team's points per game increases in the final 10 matches, while in non-championship seasons it drops noticeably, suggesting that motivation and momentum play a measurable role in title races.

