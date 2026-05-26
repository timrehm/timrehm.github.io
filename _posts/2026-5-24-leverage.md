---
layout: post
title: "Let's Look at Leverage"
date: 2026-05-24
---

Most baseball fans, whether casual, serious, approach the game with an analytical eye, or live and die by the "eye test," have at some point believed that a player was either more (or less) "clutch" than another player. I mean, can you blame someone for thinking David Ortiz had some extra clutch *skill* after the 2004 Postseason? Surely, when you watch every inning of every game of your favorite team, you will swear that some
players are clutch than average. Sometimes teams as a whole have an air of clutchness to them--the 2025 Tigers were coined the "Gritty Tigs" due to their supposed mental fortitude and comeback quality. Were they more clutch than the other teams? Maybe they measure out better in clutch situations, but did they have more clutch skill? That is a post for another time. For this post, let's just focus on players, batters to be specific.

To compare the clutchness of hitters, we need to separate what situations are high-leverage (HL) and which are low-leverage (LL). That's where the leverage index (LI) comes in. The LI we'll look at was created by Tom Tango and attempts to quantify the swing in win probability at a given game state. Indeed, much of the methodology in this book is given by Tom Tango's <a href="https://www.insidethebook.com/" target="_blank">**The Book**</a>. The LI is essentially a ratio of differences; one between the win probability of the state of interest and the average state *after* a typical out and the other between the win probability of the two states *after* a typical hit. An LI of $1.0$ measures the leverage an average game state (the average LI from a group of LIs in a randomly-selected group of game states). LI depends on the inning, score difference, number of outs, and runners on base. <a href="https://tht.fangraphs.com/crucial-situations/" target="_blank">A full description of LI can be found here</a>. Naturally, the plate appearance (PA) of a batter in the top of the 2nd with 1 out, nobody on, and winning by 4 runs will be less impactful than the PA of a batter in the bottom of the 8th with 2 outs, bases loaded, and losing by 1 run. The success of the batter in the first scenario very likely does not affect his team's win probability in the end, but the batter in the latter scenario is primed to drastically change the win probability of his team; a base hit will tie the score late in the game, and may even give them the lead. The LI of the first game state is $0.3$, while the LI of the latter game state is $7.7$. <a href="https://insidethebook.com/li.shtml#1" target="_blank">A table of the LI for all game states can be found here</a>. With respect to the weight of all other game states, I'd say this is a good metric for sifting game states with leverage, so we'll use it to separate the HL PA from the LL PA for a *batter*. 

So who's doing well in the clutch so far in 2026? (Today is May 24th, 2026.) Let's look at the [wOBA](https://library.fangraphs.com/offense/woba/) for each player who has $\geq 150$ PA. A HL PA has a LI $\geq 2.0$, and likewise a LL PA has a LI $<2.0$:

<p align="center">
  <img src="/plots/2026HLwOBA_errorbar.svg" style="max-width: 100%; width: 100%;">
</p>

The size of the data points correlate with the number of HL PA. The dahsed black line shows where HLwOBA = LLwOBA, so any batter below that line is worse (than himself) in the clutch than not in clutch, and vice versa. What does one take away from this? The weighted average of wOBA values in high-leverage situations (HLwOBA) is lower than the mean wOBA, but is within uncerainty (one standard deviation). Only around $10\%$ of PA are in high leverage. Is Aaron Judge really becoming a $.180$ wOBA hitter in the clutch? Is Cole Young, with a wOBA in low leverage situations (LLwOBA) of $.271$, one standard deviation below the mean, really becoming a $.558$ wOBA hitter in the clutch? Strictly from what we've observed? I guess. Aaron Judge has only $10$ PA in high leverage situations and has gone $1/8$ with $1$ uBB and $1$ IBB. Sure. Cole Young has gone $10/24$ with $3$ HBP and $1$ <a href="https://www.mlb.com/video/seth-lugo-ball-to-cole-young-uulxy5?q=05%2F02%2F2026%20Bottom%205th%20inning%20Seattle&cp=MIXED&qt=FREETEXT&p=0" target="_blank">weird PA that got truncated</a> (so it had to be removed) because Randy Arozarena lost track of the count and got caught sleeping between first and second. That was a poorly timed TOOTBLAN by Arozarena here; bottom of the 5th, up by 1 run, 2 outs, bases loaded... 

But over the course of the season, will these results hold? No. The sample size taken here is just too small to infer anything about the ability of any hitter. Aaron Judge will regress to his mean and maintain his elite hitter status, while Cole Young will continue to fluctuate as he accumulates more PAs in the MLB. Perhaps the Yankees' 2-9 record against teams $> .500$ could be partially attributed to Judge's slow start in the clutch. Regardless, they are 31-22, and there isn't much we can infer from this dataset. Look at the errorbars of the selected players, they are huge. The measurement unceratinty of Jarren Duran's HLwOBA is $\pm.174$ in $16$ HL PA. Despite his slow start to the season, Duran has had some clutch successes: <a href="https://www.mlb.com/video/jarren-duran-homers-4-on-a-fly-ball-to-left-field-carlos-narvaez-scores-andruw-m-dhqnfd?q=2026-05-04%20Top%20Seventh%20Inning%20Red%20Sox&cp=MIXED&qt=FREETEXT&p=0" target="_blank">a three-run homerun</a> in the top of the 7th with 0 outs and down by 2 runs (LI = $3.2$) and <a href="https://www.mlb.com/video/steven-cruz-in-play-run-s-to-jarren-duran-p1ruxn?q=2026-05-20%20Red%20Sox%20Duran&cp=CMS_FIRST&qt=FREETEXT&p=0" target="_blank">a two-run homerun</a> in the top of the 7th with 1 out and down by 1 run (LI = $2.3$). Each measurement of wOBA, whether in HL or LL, has a statistical uncertainty from the classification process of putting hitter events into multiple discrete categories (1B, 2B, 3B, HBP, etc.), so when we say Jarren Duran is sporting a $.350\pm.174$ HLwOBA, that means if we had 100 identical Jarren Durans, $68$ of them will measure a HLwOBA between $.524$ and $.176$. That's the difference between being the best hitter in the league and the worst. To calculate the uncertainty of a measured wOBA ($\sigma_{\mathrm{wOBA}}$), we use the year-to-year linear weights ($w_{i}$) <a href="https://www.fangraphs.com/tools/guts" target="_blank">found here</a> and calculate $\left\langle\mathrm{wOBA}\right\rangle$ and $\left\langle\mathrm{wOBA}^{2}\right\rangle$ as:

$$
\Large \left\langle\mathrm{wOBA}\right\rangle = \frac{1}{N_{\mathrm{PA}}}\sum_{i}w_{i}n_{i} \ \ \ \ \left\langle\mathrm{wOBA}^{2}\right\rangle = \frac{1}{N_{\mathrm{PA}}}\sum_{i}w_{i}^{2}n_{i}
$$

Here, $n_{i}$ is the number of 1B, 2B, 3B, HR, uBB, and HBP for a batter, and $N_{\mathrm{PA}}$ is the number of PA including sacrifice flies but not including reaching on errors, IBBs, sacrifice bunts, and other truncated PA. The equation for $\sigma_{\mathrm{wOBA}}$ is given as:

$$
\Large \sigma_{\mathrm{wOBA}} = \sqrt{\frac{\left\langle\mathrm{wOBA}^{2}\right\rangle-\left\langle\mathrm{wOBA}\right\rangle^{2}}{N_{\mathrm{PA}}}}
$$

What about over the course of a full season? Here is how the batters in 2025 with $\geq 400$ PA performed in HLwOBA and LLwOBA:

<p align="center">
  <img src="/plots/2025HLwOBA_errorbar.svg" style="max-width: 100%; width: 100%;">
</p>

Colt Keith has the highest HLwOBA in this sample across $25$ PA... a member of the Gritty Tigs?... and Aaron Judge is still "worse" than himself in the clutch, but his HLwOBA is almost one standard deviation above average. The sample size is still quite too small. The average HLwOBA is again lower than the overall average wOBA, which should be expected since the majority of HL PA occur in the 8th and 9th innings, when opposing teams normally put in their best relievers. Likewise, we expect the average LLwOBA to be very close to the average wOBA since around $90\%$ of PA are in low leverage. So let's try and expand the sample size and see if we can infer any clutch skill. Let's look at the HL and LL performance of each player with $\geq 400$ PA in each of the last four seasons (2022-2025):

<p align="center">
  <img src="/plots/2022-25HLwOBA_errorbar.svg" style="max-width: 100%; width: 100%;">
</p>

$76$ different players qualified. The average wOBA of this sample is larger than an entire league-averaged wOBA, likely due to the fact that if you are in this list and have $1600$ PA across 4 seasons, you are probabaly a pretty good hitter. Here are the top and bottom 6 hitters in HLwOBA:

$$
\Large
\begin{array}{|c|c|c|c|}
\hline
\mathrm{Top \ 6} & \mathrm{HLwOBA} & \mathrm{Bottom \ 6} & \mathrm{HLwOBA} \\
\hline
\mathrm{Aaron \ Judge}& .400\pm.045 & \mathrm{Taylor \ Ward} & .250\pm.030 \\
\hline
\mathrm{Shohei \ Ohtani}& .399\pm.042 & \mathrm{Brandon \ Marsh} & .253\pm.030\\
\hline
\mathrm{Matt \ Olson}&.395\pm.038 & \mathrm{Marcus \ Semien} & .254\pm.030 \\
\hline
\mathrm{Vladimir \ Guerrero \ Jr.}&.391\pm.033  & \mathrm{Dansby \ Swanson} & .254\pm.030\\
\hline
\mathrm{Corey \ Seager} &.387\pm.045 & \mathrm{Matt \ Chapman} &.255\pm.028 \\
\hline
\mathrm{Carlos \ Santana} &.381\pm.037 & \mathrm{Austin \ Riley} & .262\pm.034\\
\hline
\end{array}
$$

This isn't really mind-blowing. Some of the league's best hitters measure the highest HLwOBA, and the players with the lowest HLwOBAs are not necessarily bad hitters, but don't come to mind as the most threatening offensive talent, and maybe are more regarded for their defensive attributes. Perhaps what is of interest is the difference between a player's HLwOBA and LLwOBA $\left(\Delta\mathrm{wOBA}\right)$, which could reveal the ability of a player to become better or worse than themself in the clutch. A positive $\Delta\mathrm{wOBA}$ indicates better performance in the clutch, and vice versa when $\Delta\mathrm{wOBA}$ is negative. Calculating $\Delta\mathrm{wOBA}$ is simply:

$$
\Large \Delta\mathrm{wOBA}\pm\sigma_{\Delta\mathrm{wOBA}} = \left(\mathrm{HLwOBA}-\mathrm{LLwOBA}\right)\pm\sqrt{\sigma_{\mathrm{HLwOBA}}^{2}+\sigma_{\mathrm{LLwOBA}}^{2}}
$$

Looking at the top and bottom 6 in $\Delta\mathrm{wOBA}$:

$$
\Large
\begin{array}{|c|c|c|c|}
\hline
\mathrm{Top \ 6} & \Delta\mathrm{wOBA} & \mathrm{Bottom \ 6} & \Delta\mathrm{wOBA} \\
\hline
\mathrm{Carlos \ Santana}& .080\pm.038 & \mathrm{Taylor \ Ward} & -.097\pm.032\\
\hline
\mathrm{Jonah \ Heim}& .058\pm.036 & \mathrm{Austin \ Riley} & -.096\pm.036\\
\hline
\mathrm{Ryan \ McMahon}&.035\pm.037 & \mathrm{Matt \ Chapman} & -.087\pm.031\\
\hline
\mathrm{J.P. \ Crawford}&.033\pm.033  & \mathrm{Paul \ Goldschmidt} & -.083\pm.033\\
\hline
\mathrm{Matt \ Olson} &.033\pm.040 & \mathrm{Brandon \ Marsh} &-.082\pm.033\\
\hline
\mathrm{Adolis \ García} &.032\pm.035 & \mathrm{Bryce \ Harper} & -.074\pm.035\\
\hline
\end{array}
$$

Over the course of four seasons, Carlos Santana appears to have a knack for the clutch despite being 1-$\sigma$ below average in low leverage situations. The average $\overline{\Delta\mathrm{wOBA}}=-.021\pm.034$, so this group of batters performs slightly worse than themselves on average in high leverage situations. Not too unexpected, as the likelihood of a high caliber reliever opposing them is higher, or a platoon is in effect, e.g. a left-handed pitcher is brought in during a high leverage spot to face one of our left-handed batters. Interesting to note that #1 and #2 in $\Delta\mathrm{wOBA}$, Carlos Santana and Jonah Heim, are both switch hitters, so they will always have the platoon advantage when it comes to the handedness of the pitcher in high leverage situations. So can we attribute any of these $\Delta$wOBA measurements to an actual increase in a player's skill in the clutch, or are the results attributed solely to statistical uncertainty? For a given player $P$, we can assume that the variation of $P$'s $\Delta\mathrm{wOBA}$ from the mean is equal to the sum of the statistical variance in the measurement and the variance in that player's clutch skill ($\sigma_{\mathrm{skill}}^{2}$). The clutch skill is a measure of the contribution to a player's measured $\Delta\mathrm{wOBA}$ that is not accounted for by statistical uncertainty, and $\sigma_{\mathrm{skill}}$ is a measure of the spread of that player's skill in the clutch. For example, if $P$ has a measured clutch skill of $+.002\pm.003$, then we would expect $P$ to perform $.002$ points *better* than their expected wOBA in clutch situations, but we are only $68\%$ certain that $P$'s true clutch skill is between $-.001$ and $+.005$. To infer the clutch skill of individual players, we'll need to know the variance in clutch skill across all players in the group. Writing this out for player $P$ looks like:

$$
\Large  \sigma_{\mathrm{skill}, \ P}^{2} = \left(\Delta\mathrm{wOBA}_{P}-\overline{\Delta\mathrm{wOBA}}\right)^{2}-\tilde{N}\sigma_{\Delta\mathrm{wOBA}, \ P}^{2} 
$$

Since we want to exclude $P$'s contribution to $\overline{\Delta\mathrm{wOBA}}$ when considering his skill variance, we include the factor $\tilde{N} = 1-N_{\mathrm{eff}}/N_{\mathrm{tot}},$ where $1/N_{\mathrm{eff}} = 1/N_{\mathrm{HL \ PA}}+1/N_{\mathrm{LL \ PA}}$ and $N_{\mathrm{tot}}$ is the sum of $N_{\mathrm{eff}}$ for all players. To find the weighted average of clutch skill variances across the entire group, we'll also need the uncertainty in $\sigma_{\mathrm{skill}, \ P}^{2}$, which equals the *total* observed variance multiplied by $\sqrt{2}:$

$$
\Large \sigma\left(\sigma_{\mathrm{skill}, \ P}^{2}\right) = \sqrt{2}\left(\sigma_{\Delta\mathrm{wOBA}, \ P}^{2} + \sigma_{\mathrm{skill}}^{2}\right)
$$

Therefore, the clutch skill variance (and its uncertainty) of the entire group is:

$$
\Large \sigma_{\mathrm{skill}}^{2} = \frac{\sum_{P}\frac{\left(\Delta\mathrm{wOBA}_{P}-\overline{\Delta\mathrm{wOBA}}\right)^{2}-\tilde{N}\sigma_{\Delta\mathrm{wOBA}, \ P}^{2}}{2\left(\sigma_{\Delta\mathrm{wOBA}, \ P}^{2} + \sigma_{\mathrm{skill}}^{2}\right)^{2}}}{\sum_{P}\frac{1}{2\left(\sigma_{\Delta\mathrm{wOBA}, \ P}^{2} + \sigma_{\mathrm{skill}}^{2}\right)^{2}}} \pm \sqrt{\frac{2}{\sum_{P}\left(\sigma_{\Delta\mathrm{wOBA}, \ P}^{2} + \sigma_{\mathrm{skill}}^{2}\right)^{-2}}}
$$

This equation is self-referential, as the variance of each player's individual skill variance is a function of the *total* variance, so one would need to solve this with a root-finder or recursively until a self-consistent value for $\sigma_{\mathrm{skill}}^{2}$ is found. Solving this for our $76$ batters yields $\sigma_{\mathrm{skill}}^{2}$ = $.00012\pm.00022$. That means that our population has a clutch skill standard deviation $\sigma_{\mathrm{skill}}=.011$ points in wOBA. From what we *measured*, we found the average $\Delta\mathrm{wOBA} = -.021\pm.034$ from statistical uncertainty, but now we find the average $\Delta$wOBA *skill* equals $-.021\pm.011$. We can estimate each player's clutch skill with respect to the population of players by regressing each player's performance to the mean. We will take each player's $\Delta\mathrm{wOBA}$ and interpret it as his measured clutch skill, and then regress to the population mean of clutch skill. Take Jonah Heim, his *measured* clutch skill is $.058\pm.036$. We can regress his clutch skill to the mean, which weighs the measured clutch skill and population mean by the inverse of each measurement's variance. This looks like:

$$
\Large 
\begin{align*}
\mathrm{clutch \ wOBA \ skill} &= \frac{-.021/.011^{2}+.058/.036^{2}}{1/.011^{2}+1/.036^{2}}\\
&= -.014
\end{align*}
$$

Despite us measuring a $.058\,\Delta\mathrm{wOBA}$, which is *seven* standard deviations above the mean clutch skill, when we regress, we find that Jonah Heim turns out to be a $-.014\,\Delta\mathrm{wOBA}$ hitter, so we expect Jonah Heim to perform $.014$ wOBA points *lower* than his low leverage wOBA, which is only $.0065$ wOBA points above the mean. This is how we'll quote expected clutch skill, as the number of wOBA points above the observed mean clutch skill. Doing this for every batter in our group, here's the list of the top and bottom 10 in clutch skill:

$$
\Large
\begin{array}{|c|c|c|c|}
\hline
\mathrm{Top \ 10} & \mathrm{Expected \ clutch \ skill} & \mathrm{Bottom \ 10} & \mathrm{Expected \ clutch \ skill}\\
\hline
\mathrm{Carlos \ Santana}& .0075 & \mathrm{Taylor \ Ward} & -.0077\\
\hline
\mathrm{Jonah \ Heim}& .0065 & \mathrm{Matt \ Chapman} & -.0074\\
\hline
\mathrm{J.P. \ Crawford}&.0053 & \mathrm{Austin \ Riley} & -.0064\\
\hline
\mathrm{Adolis \ García}&.0046  & \mathrm{Brandon \ Marsh} & -.0060\\
\hline
\mathrm{Vladimir \ Guerrero \ Jr.} &.0045 & \mathrm{Paul \ Goldschmidt} &-.0060\\
\hline
\mathrm{Ryan \ McMahon} &.0045 & \mathrm{Marcus \ Semien} & -.0054\\
\hline
\mathrm{Steven \ Kwan} &.0042 & \mathrm{Dansby \ Swanson} & -.0053\\
\hline
\mathrm{Tommy \ Pham} &.0040 & \mathrm{Bryce \ Harper} & -.0047\\
\hline
\mathrm{Matt \ Olson} &.0038 & \mathrm{Seiya \ Suzuki} & -.0045\\
\hline
\mathrm{Brandon \ Nimmo} &.0038 & \mathrm{Randy \ Arozarena} & -.0044\\
\hline
\end{array}
$$

Carlos Santana again reigns supreme. From the measured results, we would expect him to hit $.0075$ wOBA points higher in the clutch than the average. In 2026, he played 8 games and then strained his adductor, so there is absolutely no way to project this result into this season. Perhaps we should look at the clutch skill for players between 2022-2024 and see if we could have predicted their clutch skill in 2025? To do this, we'll re-do all of the calculations above for only the 2022-2024 seasons, add their clutch skill to their 2025 LLwOBA to formulate our expected HLwOBA, and see how the top and bottom 10 values align with what they posted. I am not very interested in seeing how well we can predict a player who is indifferent to the clutch remains indifferent to the clutch. 

Let's see the top 10:

$$
\Large
\begin{array}{|c|c|c|c|}
\hline
\mathrm{Top \ 10} & \mathrm{Expected \ HLwOBA} & \mathrm{2025 \ HLwOBA} & \mathrm{Difference}\\
\hline
\mathrm{Carlos \ Santana}& .250 & .446 & -.196\\
\hline
\mathrm{Jonah \ Heim}& .250 & .294 & -.044\\
\hline
\mathrm{J.P. \ Crawford}&.294 & .427 & -.133\\
\hline
\mathrm{Adolis \ García}&.266  & .313 & -.046\\
\hline
\mathrm{Vladimir \ Guerrero \ Jr.} &.347 &.396 &-.049\\
\hline
\mathrm{Ryan \ McMahon} &.298 & .250 & +.048\\
\hline
\mathrm{Steven \ Kwan} &.294 & .311 & -.017\\
\hline
\mathrm{Tommy \ Pham} &.276 & .447 & -.171\\
\hline
\mathrm{Matt \ Olson} &.351 &.361  & -.010\\
\hline
\mathrm{Brandon \ Nimmo} &.319 & .286 & +.033\\
\hline
\end{array}
$$

And the bottom 10:

$$
\Large
\begin{array}{|c|c|c|c|}
\hline
\mathrm{Bottom \ 10} & \mathrm{Expected \ HLwOBA} & \mathrm{2025 \ HLwOBA} & \mathrm{Difference}\\
\hline
\mathrm{Taylor \ Ward}& .311 & .312 & -.001\\
\hline
\mathrm{Matt \ Chapman}& .316 & .250 & +.071\\
\hline
\mathrm{Austin \ Riley}&.319 & .177 & +.142\\
\hline
\mathrm{Brandon \ Marsh}&.313  & .312 & +.001\\
\hline
\mathrm{Paul \ Goldschmidt} &.306 &.144 &+.162\\
\hline
\mathrm{Marcus \ Semien} &.263 & .307 & -.044\\
\hline
\mathrm{Dansby \ Swanson} &.291& .231 & +.060\\
\hline
\mathrm{Bryce \ Harper} &.338 & .323 & +.015\\
\hline
\mathrm{Seiya \ Suzuki} &.318 &.355  & -.037\\
\hline
\mathrm{Randy \ Arozarena} &.304 & .333 & -.029\\
\hline
\end{array}
$$

So, how did we do? Well, remember the HLwOBA between 2022-2025 has an uncertainty of $\pm.039$, and only $8$ of our predictions were within that range, and that is even without considering the uncertainties of the 2025 HLwOBA values. Overall, we didn't do great. We nailed Taylor Ward. He demonstrates the weakest skill in coming through in the clutch, and we predicted his high leverage performance because of it, but we severely underestimated Carlos Santana's high leverage performance. What hurts our predictive power over Carlos Santana is that he is a below average low leverage hitter, which constitutes way more of his plate appearances, but he posts considerably higher HLwOBA, so we are somewhat forced to believe he will regress. With Taylor Ward, he is a pretty average low leverage hitter, and he is worse in the clutch, which is the case for the average batter, so perhaps his performance is more standard to predict. Considering our predictive power over the rest of the group, it's quite unlikely that we can predict who will do better than their average self in the clutch. And in the end, do we really care? Aaron Judge has a $-.022$ expected clutch skill, but has the *highest* HLwOBA over that same time! Clearly, we want him hitting in high leverage situations, even if he is a worse version of himself. But perhaps Carlos Santana continues to string together 1-year deals, and is constantly traded to semi-competitive teams, because, whether teams are conscious of it or not, he has the ability to swing the win probability of a game by a lot in his team's favor when in the clutch. And as I finish this, Aaron Judge just hit <a href="https://www.mlb.com/video/judge-comes-in-clutch-for-the-yankees?q=2026-05-24%20Judge&cp=CMS_FIRST&qt=FREETEXT&p=0" target="_blank">a walk-off two-run homerun</a> in the bottom of the 9th inning of a tie game, a LI = $3.1$ success that raised his HLwOBA from .179 to .335! Clearly, large swings in HLwOBA can be affected by only a few events, and it's hard to determine whether or not someone truly has a legitimate clutch skill, but it's always fun to look. 
