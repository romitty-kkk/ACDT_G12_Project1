# ACDT_G12_Project1


ACDT Group 12 – Reassessing Digital Habits and Sleep Patterns

Project Title:

“Does Gaming Before Bed Really Ruin Your Sleep?”

Team Members:

2025089998 Seoyeon Park, 2025015950 Seoan Lee, 2025073381 Sihyun Kim, 2025036444 Shalrom Hwang, 2025032379 Jiyun Hyun




1. Research Question:

Modern society assumes that “using a smartphone before bed, especially for gaming, harms sleep.”

1️⃣ Does pre-bed gaming reduce total sleep duration?

2️⃣ Does gaming negatively affect sleep quality (PSQI)?

3️⃣ Do sleep quantity and quality actually have a positive correlation?

We tested the conventional belief that “smartphone gaming before bed ruins your sleep” through data-driven statistical analysis. 




2. Background: Challenging the Conventional Wisdom

Modern media often suggests that blue light and cognitive arousal from smartphone use, especially gaming, lead to poor sleep.
However, our preliminary study found no significant relationship between total phone-use time and sleep quality.
Hence, this project investigates whether app type (game, social, video, phone) and time of use (daytime, prebed, postbed) have differentiated effects.





3. Dataset Overview

- timeframes.csv :	Bedtime (bt_yes) and wake time (wt_today) for calculating total sleep time
  
- game.csv :	Pre-bed gaming duration
  
- social.csv :	Pre-bed social media usage
  
- video.csv :	Pre-bed video streaming usage
  
- phone.csv :	General daily and post-bed phone usage
  



4. Data Preprocessing Pipeline

- Datetime Parsing & Sleep Duration Calculation:
  
   -Convert bedtime/waketime to datetime, compute total sleep in minutes.
  
   -Correct midnight crossover (add +24h when needed).


- Outlier Removal
  
   -Keep sleep duration between 180–960 min.
  
   -Keep gaming duration between 0–480 min.


- Unit Conversion
  
    -Convert gaming time from hours → minutes if max ≤ 2.


- Data Merging
  
    -Merge timeframes, game, and phone on user_id.
  
    -Aggregate by user average (groupby.mean()).
  



5. Analysis Design

Step	Model Type	/ Purpose	/Variables

①	Simple Linear Regression	/Test direct relationship	/Gaming → Sleep Time

②	Polynomial Regression /	Detect nonlinear patterns	/Gaming + Gaming² → Sleep

③	Group Comparison /	T-test: High vs Low gamers	/Prebed gaming median split

④	Mediation Model	/ Indirect effect via bedtime	/Gaming → Bedtime → Sleep

⑤	Multiple Regression	/ Compare app types	/Game, Social, Video, Phone

⑥	Time-Based Regression /	Compare daytime/pre, post-bed	/Daytime, Prebed, Postbed




6. Visualizations
 
1️⃣ Linear Regression

"Pre-Bed Gaming vs Total Sleep Duration"

 No significant relationship (β = –0.48, p = 0.605)


2️⃣ Polynomial Fit

"Testing Nonlinearity: Gaming Time vs Sleep Duration"

Slight curve, but statistically insignificant (p = 0.455)


3️⃣ Group Comparison

"Average Sleep Time: High vs Low Gamers"

Only ~8 min difference, non-significant (p = 0.419)


4️⃣ Multiple Regression Coefficients

"Impact of Different Usage Patterns on Sleep Time"

Social & Daytime ↓ Sleep; Postbed ↑ Sleep (measurement bias)


5️⃣ Mediation Model

"Gaming → Bedtime → Sleep Duration"

No significant indirect or direct paths (β = 0.10, 0.44, –0.43)


6️⃣ 2D Histogram Heatmap

"Pre-bed Gaming vs Sleep Duration"


7️⃣ KDE Density Map

"Distribution of Average Gaming Time vs Sleep"


8️⃣ Correlation Heatmap (r, p)

"App Usage vs Sleep Indicators"

Social & Game show weak negative r, Daytime & Postbed patterns visible.




7. Interactive Results:

Explore our interactive regression and coefficient visualizations:

- Simple Linear Regression 

- Coefficient Comparison (App Type)

- Group Comparison (High vs Low Gamers)
  
- Polynomial Regression
  
- Heatmap

  



8. Key Findings

Variable	/ β	/ p-value	/ Effect

Game/ (prebed)/	–0.436	0.028	/Small negative

Social	/–0.773 /	<0.001	/Strong negative

Video	/ +0.085	/ 0.403	/Not significant

Daytime	/ –3.104	/ <0.001	/Strong negative

Postbed	/+3.120	/<0.001	/Measurement artifact


9. System Map Comparison

- Map A — Statistical Model (Empirical):

From the regression model 

Gaming before bed: β = –0.48, p = 0.605 (not significant)

Daytime use: β = –12.01, p = 0.009 (significant)

Post-bed use: β = +12.07, p = 0.009 (ambiguous direction)

Interpretation:

Longer gaming before bed does not clearly reduce sleep time.
Instead, daily smartphone overuse—especially during the day—has a stronger negative effect on total sleep.

   
- Map B — Theoretical Model (Conceptual):
   
   Explains why weak statistical links may still represent hidden causal loops

Daytime fatigue → late-night use → shorter sleep → more fatigue → repetition

Psychological & physiological factors (stress, caffeine, blue light) amplify imbalance

Core Insight:

Poor sleep arises from digital rhythm imbalance, not from a single behavior like gaming.


- Justification: Bridges the gap between quantitative evidence and theoretical reasoning:

Non-significant factors can still co-create meaningful emergent effects.

Sleep disruption is best understood as a system-level imbalance, not a single cause.

Combining Maps A + B yields a holistic model of Digital Rhythm Management, aligning data analysis with behavioral design for healthier technology use.
     

10. Executive Summary
Gaming before bed → no significant impact (p > 0.5)

Daytime smartphone use → strongest negative predictor of sleep (p = 0.001)

SNS & video → mild negative effects (p = 0.02–0.03)

Sleep duration ↔ quality → strong positive correlation (r = 0.68, p < 0.001)

“Contrary to common belief, nighttime gaming does not significantly shorten or worsen sleep.
Daytime overuse and emotional stimulation from social and video apps are stronger risk factors.”

  
11. Main Conclusions

1️⃣ Pre-bed gaming does not significantly reduce sleep time.

2️⃣ Daytime and social media use have stronger negative effects.

3️⃣ Digital rhythm imbalance — not a single activity — drives poor sleep.

4️⃣ Game use before bed has minimal physiological or behavioral impact.




12. Reinterpreting the Conventional Wisdom

“It’s not gaming that ruins your sleep — it’s your digital rhythm imbalance.”

Rather than focusing on avoiding specific activities, this study suggests maintaining balance and self-regulation across the day’s device use as the key to digital well-being.




13. Repository Contents

- ACDT_G12_Final_code_colab.ipynb:	Full Colab notebook with all preprocessing and regression steps
  
-  Exported Plotly HTML graphs
  
- PNG snapshots of key visualizations
  
- README.md	This documentation
  
- Executive Summary
  
- Comparison Map(Map A, Map B, Justification)



  
14. Tools Used

- Python 3.10
  
- Google Colab
  
- pandas, numpy, statsmodels, matplotlib, seaborn, plotly
  
- GitHub Pages for visualization publishing
  
- Canva(designing a website)
  

