# 🏆 AFCON 2025 Winner Prediction: A Data Science Approach

**Predicting the Africa Cup of Nations 2025 Champion using Historical Performance Analysis & Monte Carlo Simulation**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

---

## 📊 Project Overview

This project employs advanced statistical modeling and Monte Carlo simulation to predict the winner of the **2025 Africa Cup of Nations (AFCON)** hosted in Morocco. By analyzing comprehensive historical performance data spanning decades of AFCON tournaments, the model generates probability-based forecasts for tournament outcomes.

### Key Findings

Based on **10,000 tournament simulations**, the model predicts:

| Rank | Team | Win Probability | Semifinal Probability | Quarterfinal Probability |
|------|------|----------------|----------------------|-------------------------|
| 1 | 🇪🇬 Egypt | 19.32% | 30.26% | 45.80% |
| 2 | 🇳🇬 Nigeria | 11.19% | 20.47% | 35.69% |
| 3 | 🇨🇮 Ivory Coast | 10.78% | 19.83% | 35.63% |
| 4 | 🇨🇲 Cameroon | 10.53% | 19.21% | 34.24% |
| 5 | 🇲🇦 Morocco | 9.78% | 18.96% | 34.30% |

---

## 🎯 Methodology

### 1. Data Collection & Feature Engineering

The model incorporates multiple dimensions of team strength:

#### Historical Performance Metrics
- **All-time AFCON statistics** (qualification + group stages + pre-knockout rounds)
- Matches played, wins, draws, losses
- Goals scored and conceded
- Point-per-game averages
- Goal differential

#### Tournament Pedigree
- Total AFCON titles won
- Number of tournament appearances
- Qualification success rate (% of campaigns qualified)
- Historical performance trends

#### Contextual Factors
- **Host advantage** (Morocco receives +10% boost)
- Current 2025 tournament form
- Defensive solidity metrics (clean sheet rates)
- Attacking efficiency (goals per game)

### 2. Strength Index Calculation

Teams are ranked using a **weighted composite strength score**:

```
Strength Score = 
    0.30 × Normalized(Points Per Game) +
    0.25 × Normalized(Goal Difference) +
    0.15 × Clean Sheet Rate +
    0.10 × Qualification Success Rate +
    0.10 × Log(Tournament Appearances) +
    0.10 × Host Bonus
```

This approach mirrors clinical risk scoring systems, where multiple weighted factors combine to produce a probability estimate.

### 3. Monte Carlo Tournament Simulation

The simulation engine:
- Uses **Poisson distribution** for match goal modeling
- Accounts for relative team strengths via expected goals (xG)
- Simulates complete tournament structure:
  - Group stage (6 groups × 4 teams)
  - Round of 16 qualification (top 2 + 4 best 3rd place teams)
  - Knockout stages (R16 → QF → SF → Final)
- Handles penalty shootouts probabilistically
- Runs **10,000 complete tournaments** for robust statistical inference

---

## 📁 Project Structure

```
afcon_2025_prediction/
│
├── data/
│   ├── afcon_historical_strength.csv      # Historical team statistics
│   └── afcon_2025_predictions.csv         # Model predictions
│
├── src/
│   ├── afcon_data_builder.py              # Data collection & feature engineering
│   └── afcon_simulator.py                 # Monte Carlo simulation engine
│
├── figures/
│   └── win_probability_chart.png          # Visualization of predictions
│
├── README.md                               # This file
└── requirements.txt                        # Python dependencies
```

---

## 🚀 Usage

### Prerequisites

```bash
pip install pandas numpy scipy matplotlib seaborn
```

### Running the Analysis

1. **Build Historical Dataset**:
```bash
python src/afcon_data_builder.py
```

2. **Run Monte Carlo Simulation**:
```bash
python src/afcon_simulator.py
```

3. **View Results**:
Results are saved to:
- `data/afcon_2025_predictions.csv` (full results table)
- `figures/win_probability_chart.png` (visualization)

---

## 📈 Key Insights

### Why Egypt Leads

Egypt emerges as the favorite (19.32%) due to:
1. **Unmatched tournament pedigree**: 7 AFCON titles (most all-time)
2. **Consistent excellence**: 26 tournament appearances, 111 matches played
3. **Strong current form**: Perfect record in AFCON 2025 (2W-0D-0L)
4. **Historical dominance**: Highest points-per-game (2.018) among qualified teams

### Morocco's Host Advantage

Morocco ranks 5th (9.78%) despite hosting because:
- Only 1 AFCON title historically (1976)
- Moderate historical win rate compared to Egypt, Nigeria, Cameroon
- **However**: Host nations have won AFCON 11 times historically (47% success rate)

### Dark Horses

Teams with lower probabilities but historical upset potential:
- **Algeria** (6.44%): 2 titles, strong recent form
- **Senegal** (5.39%): Recent champions (2021), improving trajectory
- **DR Congo** (5.36%): 2 historical titles, unpredictable in knockouts

---

## 🧪 Model Validation & Limitations

### Strengths
✅ Grounded in 65+ years of AFCON historical data  
✅ Transparent, interpretable methodology  
✅ Accounts for both long-term strength and recent form  
✅ Robust simulation approach (10,000 iterations)

### Limitations
⚠️ Cannot predict injuries, tactical changes, or referee decisions  
⚠️ Simplified group draw mechanics (actual bracket structure varies)  
⚠️ Does not incorporate player-level statistics (squad depth, star power)  
⚠️ Knockout football inherently high-variance (upsets are common)

This is a **data-driven baseline prediction**, not a deterministic forecast. Football tournaments remain beautifully unpredictable.

---

## 🔬 Clinical-Data Science Parallel

As a physician and data scientist, I recognize the parallels between this work and clinical prediction models:

| Clinical Medicine | Football Analytics |
|-------------------|-------------------|
| Patient history (comorbidities, past illnesses) | Team history (titles, appearances) |
| Current vital signs | Current tournament form |
| Risk scoring (APACHE, SOFA) | Strength index calculation |
| Prognostic uncertainty | Win probability distribution |
| Evidence-based, not deterministic | Data-driven, not certain |

Both fields require balancing historical patterns, current state, and inherent uncertainty to make informed probabilistic forecasts.

---

## 📚 Data Sources

- Historical AFCON statistics: Wikipedia, CAF Official Records, Sports Reference
- Current tournament results: AfricaSoccer.com, official AFCON 2025 fixtures
- FIFA rankings and team metadata: FIFA.com, Transfermarkt

---

## 👨‍⚕️🔬 About the Author

**Dr. Victor Prefa**
- Medical Officer | Data Scientist
- MPH (University of Roehampton) | MSc Data Science & Business Analytics (Deakin University, Distinction)
- 17+ years clinical experience | Transitioning to Healthcare Data Science
- Expertise: Machine Learning, Big Data Analytics, Clinical Research

**Connect with me:**
- LinkedIn: [linkedin.com/in/victor-prefa](#)
- GitHub: [github.com/victor-prefa](#)
- Email: victor.prefa@example.com

---

## 📝 License

This project is licensed under the MIT License.

---

## 🙏 Acknowledgments

- CAF (Confederation of African Football) for tournament data
- The global football analytics community
- Claude AI for technical assistance in code development

---

## 📊 Citation

If you use this work in your research or projects, please cite:

```
Prefa, V. (2025). AFCON 2025 Winner Prediction: A Data Science Approach.
GitHub repository: https://github.com/victor-prefa/afcon-2025-prediction
```

---

**⚽ May the best team win! 🏆**
