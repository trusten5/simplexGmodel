# simplexGmodel

A simple Expected Goals (xG) model built with StatBomb open event data. Trained on shot distance using logistic regression, with an interactive Streamlit app for exploring predictions by field position.

This was a personal project to learn how xG models work from the ground up — before getting into more complex spatiotemporal modeling.

---

## What is xG?

Expected Goals (xG) is a metric used in soccer analytics to quantify the quality of a shot. It represents the probability that a shot results in a goal based on historical data. A shot from 5 yards out might have an xG of 0.7; a long-range effort might be 0.03.

---

## How It Works

1. **Data** — Uses StatBomb open event data (freely available JSON files)
2. **Feature** — Shot distance from goal, calculated from (x, y) coordinates on a 120×80 pitch
3. **Model** — Logistic regression trained to predict P(goal) given distance
4. **App** — Streamlit interface lets you input any pitch coordinate and see the predicted xG

### Limitations
This is intentionally simple — distance alone is a weak predictor. A full xG model would include shot angle, body part, assist type, game state, and more. This was a baseline to understand the fundamentals before building more complex models.

---

## Running Locally

```bash
pip install -r requirements.txt
streamlit run newapp.py
```

---

## Tech Stack

- Python
- scikit-learn (logistic regression)
- StatBomb open data
- Streamlit
- pandas, numpy

---

## Background

Built this to understand xG modeling from scratch using real match data. Led to deeper work in spatiotemporal soccer analytics — building production xG/xA models on 3.2M+ events for MLS and NCAA teams.
