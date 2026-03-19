# Chicago Crime Arrest Prediction

> **University of Chicago | MACSS**  
> Author: Yi Wang

---

## Overview

This project applies supervised machine learning to predict whether a reported crime in Chicago results in an arrest, using 1.4 million crime records from 2018–2023. The analysis is grounded in **Routine Activity Theory** and **Social Disorganization Theory**, treating arrest outcomes not just as a classification problem but as a lens into how crime type, location, and time interact to shape policing outcomes.

**Research Question:**  
Which crime-level and contextual features are most predictive of arrest outcomes, and what do model failures reveal about the structural patterns of policing in Chicago?

---

## Data

**Source:** [Chicago Data Portal — Crimes Dataset](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)

| Detail | Value |
|---|---|
| Records | 1.4 million |
| Time range | 2018–2023 |
| Unit of analysis | Individual crime incident |
| Target variable | `Arrest` (binary: arrested / not arrested) |

> **Note:** The raw data file exceeds GitHub's size limit and is not included. Download `chicago_crimes_2018_2023.csv` directly from the Chicago Data Portal link above and place it in the `data/` folder to reproduce results.

---

## Methods

| Step | Description |
|---|---|
| EDA | Distribution of arrest rates by crime type, location, year, and time of day |
| Feature Engineering | Encoded crime type, location description, district, month, hour, and day of week |
| Modeling | Logistic Regression (baseline) vs. Random Forest |
| Hyperparameter Tuning | RandomizedSearchCV for Random Forest |
| Evaluation | Confusion matrix, F1 score, ROC-AUC, feature importance |
| Error Analysis | Spatial and temporal patterns in misclassification |

---

## Results

| Model | F1 Score | ROC-AUC |
|---|---|---|
| Logistic Regression | — | — |
| **Random Forest** | **0.90** | **0.96** |

**Top predictive features:**
- Crime type (e.g., narcotics offenses had consistently higher arrest rates)
- Location description (street vs. residence vs. commercial)
- Time of day and day of week
- Police district

---

## Theoretical Framing

Results are interpreted through two sociological frameworks:

- **Routine Activity Theory** — crime incidents requiring the convergence of a motivated offender, suitable target, and absence of guardianship. Time- and location-based features capturing these dynamics were among the strongest predictors.
- **Social Disorganization Theory** — district-level variation in arrest rates reflects broader patterns of neighborhood disinvestment and differential policing, not just crime severity.

---


```
## Repository Structure
├── individual_project.ipynb      # Full analysis notebook
├── final_project_presentation.pdf
├── data/                         # Add chicago_crimes_2018_2023.csv here
├── .gitignore
└── README.md
```

---

## Tools & Libraries

`Python` · `pandas` · `scikit-learn` · `matplotlib` · `seaborn` · `numpy`
