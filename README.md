# Impact of Red Cards on Goal Scoring in European Football

This project investigates whether red cards increase goal-scoring in football matches using causal inference techniques. By analyzing over 20,000 European league matches, we statistically estimate the effect of red card incidents on total goal output using within-match comparisons.

---

## Objective

To determine the **causal impact** of red cards on total goals scored during football matches by:
- Isolating the effect of red cards as "treatment events"
- Quantifying how goal-scoring rates change after red cards are issued

---

## Methodology

- **Data**:  
  - 20,370 matches from European football leagues (5 seasons)  
  - 57,750 total events including 54,019 goals and 3,731 red cards

- **Causal Inference Strategy**:  
  - Used **Average Treatment Effect on the Treated (ATT)** to compare pre- vs. post-red card segments **within the same match**
  - Controlled for confounders like team quality, weather, match importance, etc.

- **Statistical Model**:  
  - **Negative Binomial Regression** to account for goal count overdispersion  
  - Fixed effects for competitions + exposure offset (`log(Time_Remaining)`)

- **Robustness Checks**:  
  - Temporal stratification by 15-minute intervals  
  - Excluded injury time (min 45, 90)  
  - Limited to single red card games  
  - Placebo tests with random “fake” red cards

---

## Key Findings

- **Red cards cause a statistically significant increase in goals**:
  - **+0.083 goals per match (p < 0.001)** — a 3.1% uplift from baseline
  - **29.2% increase** in scoring rate after a red card (Rate Ratio = 1.292)
  - Strongest effect for early red cards (before halftime)

---

## 🔬 Future Improvements

- Incorporate match score state at red card time
- Add team strength metrics (e.g., Elo ratings)
- Extend to other match stats: possession, shots, xG
- Use instrumental variable or ML models for robustness
