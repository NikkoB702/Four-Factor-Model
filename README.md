# Four-Factor-Model
## Pac 12 Version

* Data compiled between 2013-2019
* [Data Link](https://www.kaggle.com/datasets/andrewsundberg/college-basketball-dataset)
* [Tableau Link](https://public.tableau.com/views/Pac12teamstats/FinalDashboard?:language=en-US&:display_count=n&:origin=viz_share_link)

##### Dean Oliver, a statistical consultant for the Denver Nuggets uses a four-factor model to determine an NBA team’s strengths and weaknesses. The four-factor model is described below:

## Four Factors for Team Offense

* Effective Field Goal Percentage (EFG)
    *EFG = (all field goals made + 0.5 (3-point field goals made) / (all field goal attempts)*
    
* Turnovers Committed per Possession (TPP)
    *TPP = (FGA-OR) + TO + (Y * FTA)*
    
* Offensive Rebounding Percentage (ORB)
    *ORP = 100 * (ORB * (Tm MP / 5)) / (MP *(Tm ORB + Opp DRB)*
    
* Free Throw Rate (FTR)
    *FTR = FTA/FGA*

## Four Factors for Team Defense

* Opponent’s Effective Field Goal Percentage (OEFG)
    *OEFG = (FG + 0.5 * 3P) / FGA*
    
* Defensive Turnovers Caused per Possession (DTPP)
    *DTPP = Opp (FGA-OR) + TO + (Y * FTA)*
    
* Defensive Rebounding Percentage (DRP)
    *DRP = 100 * (DRB * (TM MP / 5)) / (MP * (Tm DRB + Opp ORB))*
    
* Opponent’s Free Throw Rate (OFTR)
    *OFTR = Opp FTA/FGA*
    
    
What’s been documented is the little correlation between the four-factor model.  Citing Wayne Winston’s book Mathletics I’ll create visualizations that will transcend his results from using regression to evaluate four independent variables identified.

* EFG-OEFG
* TPP-DTPP
* ORP-DRP
* FTR – OFTR

Wayne’s conclusion was able to explain 91% of the variation in the number of games won. 

*Games won = (Intercept Coefficient) + (Shooting Dev. Coefficient) (EFG-OEFG) + (Turnover Dev. Coefficient) (TPP-DDTPP) + (Rebounding Dev. Coefficient) (ORP – DRP) + (Free Throw Dev. Coefficient) (FRT – OFTR)*

To measure the impact of the four factors on wins, we can look at the correlations between the four factors and wins:

* EFG -OEFG has a .85 correlation with wins and by itself explains 71% of the variation in wins.
* TPP - DTPP has a .38 correlation with wins and by itself explains 15% of the variation in wins.
* ORP - DRP has a .25 correlation with wins and by itself explains 6% of the variation in wins.
* FTR - OFTR has a .01 correlation with wins and by itself explains none of the variations in wins.

Keeping in mind that these algorithms are created with the purpose of optimizing NBA team performance, I decided to visualize these independent variables against the Pac-12 to see if any correlation exists. Here are my results.


![Total_Wins](https://user-images.githubusercontent.com/80132877/223833969-b8429add-0742-4f2b-bcff-0a01f27502a8.png)

In the image above we can see the total amount of wins per team in order. 


This image describes EFG over OEFG. We see similar results to the correlation results listed above. Teams with higher success tend to have higher effective field goal percentages while holding their opponent to a lower mark. 


![EFG_OEFG_Splits](https://user-images.githubusercontent.com/80132877/223834346-96a0449d-cbbe-4e58-85b2-475a82d1be32.png)



This image describes TPP over DTPP. The top three teams in the Conference utilize this to their advantage. We see however that Utah and Colorado can achieve wins while having a negative TPP/DTPP split. Briefly we see this lines up with Wayne’s correlation results. 


![TPP_DTPP_Splits](https://user-images.githubusercontent.com/80132877/223834481-80e843a8-df6f-41a2-9d96-5be069f3883f.png)



This image describes ORP over DRP. Arizona reigns king again as they use this key metric to their advantage once again. Colorado has a similar split differential with different results. Looking across the landscape we can see the top half of the Conference generally uses this metric to their advantage while the bottom half has nearly equal or negative splits


![ORP_DRP_Splits](https://user-images.githubusercontent.com/80132877/223834628-69f44d82-4a50-4213-beba-d5c67cd4ec02.png)



This image describes FTR over OFTR. We see generally that a level of success in this metric can create positive results, however the weight attached to these results is rather light. It is nice to have a wide split in this metric, of course, but it’s not a deal breaker regarding overall success. 


![FTR_OFTR_Splits](https://user-images.githubusercontent.com/80132877/223834810-8e42348d-1d95-4913-9346-4af48254f96b.png)



Arizona and their success start to become defined at this moment. The Wildcats have positive splits in every category. Colorado starts to paint an interesting picture regarding Wayne’s correlation results. The Buffaloes have great positive results in the metrics that hold little weight. The key metric, being EFG-OEFG, is where Colorado becomes stagnant. This provides validity to Wayne’s correlation results. Conversely, Washington State has negative results in all four key metrics and therefore ranks last in the Conference. Wazzu what are you doing?



##### How could we truncate these four metrics into one overall metric? One option is to use adjusted offensive efficiency (ADJOE) over adjusted defensive efficiency (ADJDE).

*ADJOE = (Players Points * Total FG%) + Opp Differential = 1/5 of possessions – Times Fouled + FTM * FT% * (Official Adjusted Players Offensive Withstand)*

*ADJDE = (Players Steals * Blocks) + Opp Differential = 1/5 of possessions – Times blown by + Deflections * (Official Adjusted Players Defensive Withstand)*


In this image we see a clear-cut correlation between success and ADJOE/ADJDE splits. This key metric can be used as the baseline qualitative metric to define a team’s level of success. 



![ADJOE_ADJDE_Splits](https://user-images.githubusercontent.com/80132877/223835272-245717c5-0c0c-48f3-8ec9-5927ec988386.png)


I used the Pac-12 for two basic reasons, one I’m a big fan of the Oregon Ducks and the Pac-12 in general. Two, I wanted a smaller sample size to isolate any transcending patterns. Many other variables exist in this space, and many avenues should be examined for more transparency. One metric is tempo, which correlates to my reasoning behind isolating the Pac-12. 

*Tempo = Total Points / Total Possessions*


In this image we see that tempo is mostly even across the board and has no weight in this scenario when determining success. 


![Tempo](https://user-images.githubusercontent.com/80132877/223835594-674cf461-1f54-4c0f-9668-d708bb4085b1.png)





