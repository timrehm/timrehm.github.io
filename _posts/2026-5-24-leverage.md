---
layout: post
title: "Let's Look at Leverage"
date: 2026-05-24
---

Most baseball fans, whether casual, serious, approach the game with an analytical eye, or live and die by the "eye test," have at some point believed that a player was either more (or less) "clutch" than another player. I mean, can you blame someone for thinking David Ortiz had some extra clutch *skill* after the 2004 Postseason? Surely, when you watch every inning of every game of your favorite team, you will swear that some
players are clutch than average. Sometimes teams as a whole have an air of clutchness to them--the 2025 Tigers were coined the "Gritty Tigs" due to their supposed mental fortitude and comeback quality. Were they more clutch than the other teams? Maybe they measure out better in clutch situations, but did they have more clutch skill? That is a post for another time. For this post, let's just focus on players, batters to be specific.

To compare the clutchness of hitters, we need to separate what situations are high-leverage (HL) and which are low-leverage (LL). That's where the leverage index (LI) comes in. The LI we'll look at was created by Tom Tango and attempts to quantify the swing in win probability at a given game state. Indeed, much of the methodology in this book is given by Tom Tango's <a href="https://www.insidethebook.com/" target="_blank">**The Book**</a>. The LI is essentially a ratio of differences; one between the win probability of the state of interest and the average state *after* a typical out and the other between the win probability of the two states *after* a typical hit. An LI of 1.0 measures the leverage an average game state (the average LI from a group of LIs in a randomly-selected group of game states). LI depends on the inning, score difference, number of outs, and runners on base. <a href="https://tht.fangraphs.com/crucial-situations/" target="_blank">A full description of LI can be found here</a>. Naturally, the plate appearance (PA) of a batter in the top of the 2nd with 1 out, nobody on, and winning by 4 runs will be less impactful than the PA of a batter in the bottom of the 8th with 2 outs, bases loaded, and losing by 1 run. The success of the batter in the first scenario very likely does not affect his team's win probability in the end, but the batter in the latter scenario is primed to drastically change the win probability of his team; a base hit will tie the score late in the game, and may even give them the lead. The LI of the first game state is 0.3, while the LI of the latter game state is 7.7. <a href="https://insidethebook.com/li.shtml#1" target="_blank">A table of the LI of all game states can be found here</a>. With respect to the weight of all other game states, I'd say this is a good metric for sifting game states with leverage, so we'll use it to separate the HL PA from the LL PA for a *batter*. 

So who's doing well in the clutch so far in 2026? (Today is May 24th, 2026.) Let's look at the [wOBA](https://library.fangraphs.com/offense/woba/) for each player who has $\geq$150 PA. An HL PA has an LI $\geq$ 2.0, and likewise an LL PA has an LI $<$ 2.0:

<p align="center">
  <img src="/plots/2026HLwOBA.svg" style="max-width: 100%; width: 100%;">
</p>

What does one take away from this? The weighted average of wOBA values in high-leverage situations (HLwOBA) is lower than the mean wOBA, but is within uncerainty (one standard deviation). Only around 10$\%$ of PA are in high leverage. Is Aaron Judge really becoming a .180 wOBA hitter in the clutch? Is Cole Young, with a weighted average wOBA in low-leverage situations (LLwOBA) of .271, one standard deviation below the mean, becoming a .558 wOBA hitter in the clutch? Strictly from what we've observed? I guess. Aaron Judge has only 10 PA in high-leverage situations and has gone 1/8 with 1 uBB and 1 IBB. Sure. Cole Young has gone 10/24 with 3 HBP and 1 weird PA that got truncated (so it had to be removed) because Randy Arozarena lost track of the count and got caught sleeping between first and second: <a href="https://www.mlb.com/video/seth-lugo-ball-to-cole-young-uulxy5?q=05%2F02%2F2026%20Bottom%205th%20inning%20Seattle&cp=MIXED&qt=FREETEXT&p=0" target="_blank">play found here</a>. That was a poorly timed TOOTBLAN by Arozarena here; bottom of the 5th, up by 1 run, 2 outs, bases loaded... 

But over the course of the season, will these results hold? No. The sample size taken here is just too small to infer anything about the ability of any hitter. Aaron Judge will regress to his mean, just like Cole Young will. Perhaps the Yankees' 2-9 record against teams $>$.500 could be partially attributed to Judge's slow start in the clutch. Regardless, they are 31-22, and there isn't much we can infer from this dataset, but is fun to look at nonetheless.

What about over the course of a full season? Here are how the 2025 batters with $>$400 PA performed in HLwOBA and LLwOBA:

<p align="center">
  <img src="/plots/2025HLwOBA.svg" style="max-width: 100%; width: 100%;">
</p>
