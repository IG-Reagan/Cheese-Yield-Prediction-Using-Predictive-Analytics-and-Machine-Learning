# Predictive Yield Modeling for Artisan Cheesemaking - a Digital Twin Framework

## Project Overview: Bridging Artistry and Analytics
Created December 2022 / Presented at the Operational Research Society Annual Conference OR66 in Bangor, Wales (2024).

This project develops an advanced predictive machine learning model to provide British cheesemakers with **deeper, actionable insights** into the factors driving product yield and quality, addressing the high variability inherent in biological food manufacturing.

The core challenge in artisan contexts (like cheese, wine, and fermented goods) is the complex interplay between:
1.  **Biological Uncertainty:** Fluctuations in raw materials (milk protein, microbial activity) and environmental conditions that impact the process.
2.  **Tacit Expertise:** Quality assessment often relies on the nuanced, sensory-driven judgment of expert graders (affineurs), which is rarely formalised or documented in a transferable way.

By integrating hundreds of process variables from industrial control systems (PLCs, SCADA) and laboratory checks, this project aims to create a **predictive framework** that can serve as the foundation for a **Digital Twin** - allowing cheesemakers to anticipate product outcome and optimise the make process in real-time.

This modeling approach is highly transferable and applicable to other high-variability production processes across the food and beverage industry.

---

## Project Goal

The primary objective was two-fold:

1.  **Insight Generation:** Identify and quantify the influence of granular make-process variables on final cheese yield.
2.  **Predictive Model Development:** Build a robust regression model capable of accurately forecasting yield, serving as a core component of a future digital twin for decision support.

---

## Methodology: Two Iterations to Deep Insight

The project employed an iterative development strategy, gradually increasing the complexity and granularity of features to move from general observations to expert-level insights.

| Iteration | Feature Set | Primary Objective | Outcome & Insight |
| :--- | :--- | :--- | :--- |
| **Iteration 1 (v1.ipynb)** | ~30 High-Level Features (`Dataset.csv`) | Develop initial proof-of-concept and establish baseline prediction accuracy. | The model confirmed existing knowledge (e.g., milk fat/protein ratio is crucial) but provided **no novel, actionable insights** that were new to the experienced cheesemaking team. |
| **Iteration 2 (KTP Project - Cheese Yield Prediction.ipynb)** | **~85 Granular Features** (`Cheesemake_dataset_v3.5.1.csv`) | Dive deeper into process timings, temperature gradients, and ingredient dosing ratios to uncover latent variables. | The comprehensive feature set delivered **highly useful and novel insights** that directly addressed the team's operational challenges, significantly improving the yield prediction framework. |

### Data Sources & Features

The model utilises proprietary data covering the entire cheesemaking lifecycle, including:
* **Raw Material Inputs:** Milk volume, fat percentage, protein percentage.
* **Process Variables (85+ features):** Rennet temperature and activity, flocculation duration, cut-time, scald start/end times, pitch acidity/pH/temperature, and various time-based ratios (e.g., rennet-to-salt time).
* **Target Variable:** Final Cheese Yield (by weight).

---

## Technical Implementation

The predictive model was developed using a robust machine learning workflow implemented in Python.

### Technologies Used

| Category | Tool / Library | Purpose |
| :--- | :--- | :--- |
| **Model** | Scikit-learn (Random Forest, Gradient Boosting) | Predictive model development and tuning. |
| **Data Handling** | Pandas, NumPy | Data ingestion, cleaning, transformation, and feature engineering. |
| **Visualisation** | Matplotlib, Seaborn | Exploratory Data Analysis (EDA) and feature importance visualization. |
| **Environment** | Jupyter Notebook (Python) | Iterative development and reporting. |

### Key Modeling Steps

1.  **Data Curation & Feature Engineering:** Extensive work was required to clean, normalise, and engineer time-based features and ratios from the raw sensor logs.
2.  **Feature Selection:** Importance techniques (e.g., Permutation Importance) were used to identify the most influential features among the 85 available variables, ensuring the final model was interpretable.
3.  **Model Training & Evaluation:** Regression models were trained to predict `Yield by Weight`, focusing on metrics relevant to production accuracy (e.g., Root Mean Squared Error).
4.  **Actionable Insight Extraction:** The final model's coefficients and feature importance rankings were translated into tangible recommendations for process adjustments.

---

## Future Vision: The Digital Twin

The successful development of this predictive model serves as the foundational **"brain"** for a full-scale Digital Twin system.

In future iterations, this model will be improved to generalise better and integrated into a real-time dashboard that allows cheesemakers to:

* **Predictive Forecasting:** Input current make-process variables and receive an instantaneous yield prediction.
* **Scenario Simulation:** Adjust variables (e.g., "What if I scald at 38°C instead of 40°C?") and see the predicted impact on yield and quality metrics.
* **Anomaly Detection:** Flag production runs where process inputs deviate significantly, alerting experts before a batch is compromised.
* **Standardisation:** Help formalise the "tacit judgment" of affineurs by correlating sensory outcomes with the model's key predictive features.

---

## Citing This Work

Part of this project was presented at the Operational Research Society Annual Conference OR66 in Bangor, Wales (2024).

If you utilise the methodology or results of this predictive modelling project in your own research or publications, please cite the corresponding conference abstract using the following format:

**Author-Date (Harvard) Style:**

> Iziomo, G. R., & Luo, J. (2024). *AI-powered Cheese Yield Prediction: Applying ML to Develop a "Digital Twin" for Optimising Yields in Cheese Make*. Abstract presented at **OR66: The 66th Annual Conference of the Operational Research Society**, Bangor, Wales. September 12, 2024, p. 50.

**In-Text Citation:** (Iziomo & Luo, 2024, p. 50)

The abstract is publicly available in the conference book:
[https://www.theorsociety.com/common/Uploaded%20files/Events/OR66/OR66%20Abstract%20Book\_1.pdf](https://www.theorsociety.com/common/Uploaded%20files/Events/OR66/OR66%20Abstract%20Book_1.pdf)

---

## Data and Reports Availability

Due to the **commercially sensitive** nature of the proprietary data used in this study (an Innovate UK Knowledge Transfer Partnership (KTP) project and company proprietary data), the **novel datasets** (`Cheesemake_dataset_v3.5.1.csv` and `Dataset.csv`) and the full project report are **confidential** and cannot be made public in this repository.

However, the core findings and project methodology are publicly accessible through the following material:

* **Abstract & Summary:** The final abstract is available in the **OR66 Abstract Book** (page 148).
* **Presentation:** The conference presentation materials may be available upon reasonable request.

To inquire about accessing the non-confidential version of the project report or presentation slides, please contact the lead author, **Giwa Iziomo**.
