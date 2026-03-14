# Integrative Transcriptomic and Network-Based Analysis for Identification of Key Biomarkers, Molecular Pathways, and Therapeutic Targets in HIV

## Summary

This repository contains the computational workflow developed for the study:

**Integrative Transcriptomic and Network-Based Analysis for Identifying Key Biomarkers, Molecular Pathways, and Therapeutic Targets in HIV**

The objective of this work is to integrate transcriptomic datasets and apply machine learning methods to identify discriminative genes, molecular signatures, and potential therapeutic targets associated with HIV infection.

The workflow includes data integration, unsupervised learning, supervised classification, dimensionality reduction, and feature importance analysis.

---

## Study Design

Gene expression datasets from public repositories were merged and analysed using machine learning techniques to:

* Evaluate clustering patterns among HIV subtypes and controls
* Perform dimensionality reduction using PCA
* Train classification models to distinguish HIV vs Control samples
* Identify top predictive genes using feature importance ranking

Datasets used:

* GSE24081
* GSE6740

Merged dataset:
https://drive.google.com/file/d/1632Eiy2rq4vTBcnF65i_jjkJ11T0_wyh/view?usp=drive_link
```
Merged_HIV_Data_ML.csv
```

---

## Computational Environment

Analysis was performed using:

* Python 3.12.7
* scikit-learn
* numpy
* pandas
* matplotlib
* seaborn
* scipy
* mygene

Install dependencies:

```
pip install numpy pandas matplotlib seaborn scikit-learn scipy mygene
```

---

## Workflow

### 1. Data preprocessing

* Dataset merging
* Missing value imputation
* Feature matrix generation
* Train/test split (80/20)

---

### 2. Unsupervised learning

#### Clustering

Methods:

* K-means clustering
* Hierarchical clustering
* Elbow method
* Silhouette analysis
* Euclidean distance dendrogram

Findings:

* Optimal cluster number = 3
* Clear separation between Control and HIV samples
* Sub-clustering observed among HIV-A, HIV-C, HIV-N

#### PCA

* PCA performed using sklearn.decomposition
* First 5 components explain >50% variance
* ~25 components explain ~90% variance
* Dimensionality reduction suitable for classification

---

### 3. Supervised learning

Models:

* Support Vector Machine (SVM)
* Random Forest (RF)

Modules used:

```
sklearn.svm
sklearn.ensemble
sklearn.model_selection
sklearn.metrics
```

Training procedure:

* Train/test split (80/20)
* K-fold cross-validation
* GridSearchCV hyperparameter tuning

Evaluation metrics:

* Confusion matrix
* Classification report
* ROC curve
* AUC score

---

## Results

### Classification

SVM performance:

* Accuracy: 88%
* F1 score:

  * Control: 0.86
  * HIV: 0.90
* ROC AUC: 0.96

Random Forest:

* Slightly lower accuracy
* Used for feature importance analysis

---

### Feature importance

Top 20 genes identified using Random Forest importance scores.

Top ranked genes include:

* IFI27
* ARHGEF12
* TKTL1
* CHEK1
* ASPM
* FGF16
* AQR
* BNIP3

Gene annotation performed using:

```
mygene
```

These genes may represent candidate biomarkers associated with HIV infection.

---

## Output

Generated figures include:

* Elbow plot
* PCA plot
* Hierarchical dendrogram
* Silhouette plot
* Confusion matrix
* ROC curve
* Feature importance plot

Outputs are stored in:

```
results/https://docs.google.com/document/d/1NjWsPFArc8iJaYx8EAnm-2IHWtDPQjII/edit?usp=drive_link&ouid=107503566436778870702&rtpof=true&sd=true
```

---

## Repository Structure

```
.
├── data/
│   └── Merged_HIV_Data_ML.csv
│
├── scripts/
│   ├── preprocessing.py
│   ├── clustering.py
│   ├── pca.py
│   ├── svm_model.py
│   ├── rf_model.py
│   └── feature_importance.py
│
├── results/
│   ├── figures/
│   └── tables/
│
└── README.md
```

---

## Reproducibility

To reproduce the analysis:

```
python preprocessing.py
python clustering.py
python pca.py
python svm_model.py
python rf_model.py
```

Python version used:

```
Python 3.12.7
```

---

## Notes

This repository is part of an academic research project.
Results are intended for research purposes only.

---

## Author

Agrani Perera
MSc  Computational Biology
Teesside University
2025

GitHub: [https://github.com/agraniperera]




