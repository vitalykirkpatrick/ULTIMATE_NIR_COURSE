# NIR Spectroscopy Cheat Sheet

---

## Common NIR Absorptions (Approximate Wavelengths)

| Functional Group | Wavelength Range (nm) | Description |
| :--- | :--- | :--- |
| O-H (Water) | 1450, 1940 | First overtone and combination band of water |
| C-H (Alkanes) | 1700-1800, 2250-2400 | First and second overtones of C-H stretching |
| C-H (Aromatics) | 1650-1700 | First overtone of C-H stretching in aromatic rings |
| N-H (Amines, Amides) | 1500-1550 | First overtone of N-H stretching |
| C=O (Carbonyls) | 2000-2200 | Combination bands involving C=O stretching |

---

## Common Spectral Preprocessing Methods

| Method | Purpose |
| :--- | :--- |
| **Derivatives (1st, 2nd)** | Correct for baseline shifts, resolve overlapping peaks |
| **Standard Normal Variate (SNV)** | Correct for multiplicative scatter effects (particle size) |
| **Multiplicative Scatter Correction (MSC)** | Correct for multiplicative scatter effects, similar to SNV |
| **Mean Centering** | Center the data around zero, required for PCA/PLS |
| **Smoothing (e.g., Savitzky-Golay)** | Reduce random noise in the spectrum |

---

## Common Chemometric Models

| Model | Type | Common Use |
| :--- | :--- | :--- |
| **PCA (Principal Component Analysis)** | Unsupervised | Exploratory data analysis, outlier detection |
| **PLS (Partial Least Squares)** | Supervised (Regression) | Quantitative prediction of continuous variables (e.g., concentration) |
| **LDA (Linear Discriminant Analysis)** | Supervised (Classification) | Classification of samples into discrete groups |
| **SIMCA (Soft Independent Modeling of Class Analogy)** | Supervised (Classification) | Classification, particularly for one-class modeling |

---

## Calibration Model Evaluation Metrics

| Metric | Description | Ideal Value |
| :--- | :--- | :--- |
| **R² (Coefficient of Determination)** | Proportion of variance in the reference data explained by the model | Close to 1 |
| **RMSEP (Root Mean Square Error of Prediction)** | The standard deviation of the prediction errors | As low as possible |
| **Bias** | The average difference between predicted and reference values | Close to 0 |
| **RPD (Ratio of Performance to Deviation)** | Ratio of the standard deviation of the reference data to the RMSEP | > 3 for screening, > 5 for QC, > 8 for excellent |

---

## NIR Workflow Checklist

1.  **Define Problem:** Clearly state the analytical goal.
2.  **Sample Collection:** Collect a representative set of samples.
3.  **Reference Analysis:** Obtain accurate reference values for the samples.
4.  **Spectral Acquisition:** Collect NIR spectra under consistent conditions.
5.  **Data Exploration:** Use PCA to explore the data and identify outliers.
6.  **Preprocessing:** Apply appropriate spectral preprocessing methods.
7.  **Calibration:** Build a calibration model (e.g., PLS).
8.  **Validation:** Validate the model with an independent test set.
9.  **Implementation:** Deploy the model for routine analysis.
10. **Maintenance:** Monitor and update the model as needed.
