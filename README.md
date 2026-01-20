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
Let the roll number be:

**Roll Number:** `102303785`

The transformation is defined as:

\[
z = x + a_r \sin(b_r x)
\]

Where:
\[
a_r = 0.05 \times (r \bmod 7)
\]
\[
b_r = 0.3 \times (r \bmod 5 + 1)
\]

### Computed Values
| Parameter | Value |
|---------|-------|
| \( a_r \) | 0.15 |
| \( b_r \) | 0.30 |

---

## 📐 Probability Density Function
The PDF to be learned is given by:

\[
\hat{p}(z) = c \, e^{-\lambda (z - \mu)^2}
\]

This corresponds to a **Gaussian-type distribution**, where the parameters are estimated using **exact closed-form MLE**.

---

## 🧮 Parameter Estimation (MLE)
Using Maximum Likelihood Estimation, the parameters are computed as:

\[
\mu = \frac{1}{N} \sum_{i=1}^{N} z_i
\]

\[
\sigma^2 = \frac{1}{N} \sum_{i=1}^{N} (z_i - \mu)^2
\]

\[
\lambda = \frac{1}{2\sigma^2}
\]

\[
c = \sqrt{\frac{\lambda}{\pi}}
\]

This approach ensures:
- Exact analytical solution
- Properly normalized PDF
- No numerical optimization errors

---

## ✅ Final Estimated Parameters
The learned parameters are printed during execution and also saved to a CSV file.

| Parameter | Description |
|---------|-------------|
| \( \mu \) | Mean of transformed variable |
| \( \lambda \) | Shape parameter |
| \( c \) | Normalization constant |

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

