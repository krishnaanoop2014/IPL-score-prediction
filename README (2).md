# 🏏 IPL First Innings Score Predictor

A machine learning project that predicts the final first innings score of an IPL match based on the current match state.

---

## 📁 Project Structure

```
ipl-score-predictor/
├── ipl_score_predictor.ipynb   # Main notebook
├── requirements.txt            # Dependencies
└── README.md                   # This file
```

---

## 📊 Dataset

- **Path (Kaggle):** `/kaggle/input/datasets/taiwangirl/ipl-dataset/ipl.csv`
- **Coverage:** IPL Seasons 1–12 (2008–2019)
- **Training data:** Seasons 1–9 (2008–2016)
- **Test data:** Season 10 (2017)

---

## 🤖 Models Used

| Model | Notes |
|---|---|
| Linear Regression | Best baseline performance |
| Decision Tree Regressor | Tends to overfit |
| Random Forest Regressor | Good but slower |
| AdaBoost (on LR) | Marginal improvement over LR |

> **Final model:** Linear Regression

---

## 🚀 How to Run

### On Kaggle
1. Upload or open `ipl_score_predictor.ipynb` in a Kaggle notebook.
2. Ensure the dataset is attached at the path above.
3. Run all cells — the last cell launches a **Gradio app** with a public share link.

### Locally
```bash
pip install -r requirements.txt
jupyter notebook ipl_score_predictor.ipynb
```

---

## 🎯 Gradio App Inputs

| Input | Description |
|---|---|
| Batting Team | One of 8 IPL franchises |
| Bowling Team | One of 8 IPL franchises |
| Current Over | Between 5.0 and 19.5 |
| Runs Scored | Total runs so far |
| Wickets Fallen | 0–9 |
| Runs in Last 5 Overs | Recent scoring rate |
| Wickets in Last 5 Overs | Recent pressure indicator |

**Output:** Predicted final score range (e.g. `155 – 170`)

---

## ⚠️ Notes

- Only the 8 original/consistent IPL franchises are supported.
- Predictions are most reliable between overs 10–16.
- IPL is unpredictable — treat the output as a statistical estimate!
