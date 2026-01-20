# Learn Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

## 📌 Objective
The objective of this assignment is to **estimate the parameters of a probability density function (PDF)** of a transformed variable using **Maximum Likelihood Estimation (MLE)**.

A roll-number–dependent **non-linear transformation** is applied to real-world air quality data, after which the parameters of the given PDF are learned analytically.

---

## 📊 Dataset Description
- **Dataset Name:** India Air Quality Data  
- **Source:** Kaggle  
- **File Used:** `data.csv`  
- **Feature Selected:** `no2` (Nitrogen Dioxide concentration)

Only the `no2` column is used for this assignment.

---

## 🧹 Data Preprocessing
The following preprocessing steps were applied:
- Conversion of values to numeric format
- Removal of missing (`NaN`) values
- Removal of invalid (negative) values

After preprocessing:
- **Number of valid samples (rows):** `N` (printed during execution)

---

## 🔁 Roll Number Based Transformation

**Roll Number:** 102303785

The transformation applied to the input feature x is:

z = x + a_r · sin(b_r · x)

Where:

a_r = 0.05 × (r mod 7)  
b_r = 0.3 × (r mod 5 + 1)


### Computed Values

| Parameter | Value |
|----------|-------|
| a_r      | 0.15  |
| b_r      | 0.30  |


---

## 📐 Probability Density Function

The PDF to be learned is given by:

p̂(z) = c · exp(−λ (z − μ)²)

This corresponds to a **Gaussian-type distribution**, where:
- μ is the mean
- λ controls the spread of the distribution
- c is the normalization constant


---

## 🧮 Parameter Estimation (MLE)

Using **Maximum Likelihood Estimation (MLE)**, the parameters are computed as follows:

Mean:
μ = (1 / N) · Σ zᵢ

Variance:
σ² = (1 / N) · Σ (zᵢ − μ)²

Lambda:
λ = 1 / (2σ²)

Normalization constant:
c = √(λ / π)

This approach ensures:
- Exact analytical solution
- Properly normalized PDF
- Deterministic and reproducible results


---

## ✅ Final Estimated Parameters
The learned parameters are printed during execution and also saved to a CSV file.

| Parameter | Description |
|----------|-------------|
| μ        | Mean of transformed variable |
| λ        | Shape parameter |
| c        | Normalization constant |

---

## 📈 Visualization
A histogram of the transformed variable \( z \) is plotted along with the fitted PDF curve to visually verify the quality of the estimation.

---


---

## 🧠 Key Highlights
- Roll-number dependent transformation applied correctly
- Exact Maximum Likelihood Estimation (no approximation)
- Clean, reproducible, and deterministic results
- Academic and submission-safe implementation

---

## ✍️ Author
**Dhruv Sethi**  
Roll Number: **102303785**

