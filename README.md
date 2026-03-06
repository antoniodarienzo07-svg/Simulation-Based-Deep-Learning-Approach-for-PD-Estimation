# Simulation-Based Deep Learning for Probability of Default (PD) Estimation

This project presents a specialized approach to Credit Risk Assessment using a Neural Network with **Expert Logic Constraints**. The project focuses on estimating the Probability of Default (PD) and performing macroeconomic stress testing using synthetic financial data.

## Project Overview
Traditional "Black-Box" neural networks can sometimes produce results that defy financial intuition (e.g., suggesting that lower debt increases risk). This project implements a **SoftRiskNet** using **PyTorch**, where weights are initialized to ensure the model follows established financial principles:
* **Positive Relationship:** Higher Debt Ratio $\rightarrow$ Higher PD.
* **Negative Relationship:** Higher Credit Score $\rightarrow$ Lower PD.

## Key Features
- **Synthetic Data Generation:** Simulates a portfolio of 2,000 customers with features like Income, Debt Ratio, and Employment years (modeled via Poisson distribution).
- **Expert-Weighted MLP:** A Multi-Layer Perceptron architecture with manual weight constraints to align with risk management theory.
- **Stress Testing Engine:** Simulates a macroeconomic shock by increasing the portfolio-wide debt ratio by +0.7 standard deviations.
- **Risk Migration Analysis:** Visualizes how systemic shocks push low-risk borrowers into high-risk buckets.

## Quantitative Results
The model successfully captures the non-linear shift in risk during a crisis:
| Metric | Baseline Scenario | Stressed Scenario | Impact |
| :--- | :--- | :--- | :--- |
| **Average PD** | 13.54% | 23.13% | **+70.89%** |
| **Portfolio Risk** | Low/Moderate | Deteriorated | Significant Shift |

The analysis shows that many borrowers sit near a "critical threshold" where small increases in leverage lead to explosive increases in default probability.

## Regulatory Context
This methodology aligns with the **Basel III framework**, specifically regarding:
* **Internal Ratings-Based (IRB) Approach:** Using internal models to estimate risk components.
* **Stress Testing:** Evaluating bank resilience against macroeconomic shocks to determine **Tier 1 Capital** adequacy.

## Technical Stack
* **Language:** Python
* **Deep Learning:** PyTorch
* **Data Analysis:** Pandas, NumPy
* **Visualization:** Matplotlib
* **Pre-processing:** Scikit-learn (StandardScaler)

## Author
**Antonio D'Arienzo** *Master's Degree in Financial Risk and Data Analysis*
