## Guaconomics - Avocado Price Predictor

<img class="project-shot" src="/images/guaconomics.png" alt="Guaconomics screen for predicting avocado prices"/>

**Project Description:**

A full-stack machine learning app that predicts U.S. avocado prices from region, type, size, and year. A Random Forest regressor serves predictions from a Flask API, and a Next.js front end turns the price into a short, tongue-in-cheek verdict.

**GitHub Repository:** [Guaconomics](https://github.com/alexkimrow/Guaconomics)

---

### What it does

The model is trained on the Hass Avocado Board dataset, about 18,000 weekly records from 2015 to 2023 across 54 U.S. regions. The app asks for size, year, conventional or organic type, and region, then returns a predicted average price.

Reported holdout metrics from the training notebook:

- Algorithm: Random Forest regressor, compared with a linear regression baseline
- R² about 0.65, RMSE about $0.22, MAE about $0.16
- 80/20 train-test split on roughly 14,600 training rows and 3,650 test rows

The interface maps that price into four tiers (Budget, Reasonable, Pricey, Splurge Zone), each with its own line of copy and a mascot expression.

---

### Stack

- **Model:** scikit-learn Random Forest, Pandas, NumPy, target encoding for region, one-hot encoding for type, StandardScaler
- **API:** Flask, `POST /predict` and `GET /health`
- **UI:** Next.js, React, Framer Motion
- **Training:** Jupyter notebook at `src/notebooks/01_train_model.ipynb`

Predictions are for the project demo. They are not a market forecast.
