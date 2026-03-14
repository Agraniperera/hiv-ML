# Integrative Transcriptomic and Network-Based Analysis for Identification of Key Biomarkers, Molecular Pathways, and Therapeutic Targets in HIV

## Summary

This repository contains the machine learning and transcriptomic analysis workflow developed for the study:

Integrative Transcriptomic and Network-Based Analysis for Identifying Key Biomarkers, Molecular Pathways, and Therapeutic Targets in HIV.

The project integrates gene expression datasets and applies unsupervised and supervised machine learning methods to identify important genes, molecular signatures, and potential therapeutic targets associated with HIV infection.

---

## Datasets

The following GEO datasets were used:

- GSE24081
- GSE6740

Merged dataset used for ML analysis:

Merged_HIV_Data_ML.csv

Missing values were handled using imputation before model training.

---

## Software Environment

Python version:
Python 3.12.7

Required packages:

- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- scipy
- mygene

Install dependencies:

pip install numpy pandas matplotlib seaborn scikit-learn scipy mygene

---

## Workflow

### Data preprocessing

- Merge datasets
- Handle missing values
- Prepare feature matrix
- Split data (80% train / 20% test)

---

### Unsupervised learning

Methods used:

- K-means clustering
- Hierarchical clustering
- Elbow method
- Silhouette analysis
- PCA (Principal Component Analysis)

Findings:

- Optimal cluster number = 3
- Separation between Control and HIV samples
- Sub-clustering for HIV-A, HIV-C, HIV-N

PCA results:

- 5 components explain >50% variance
- ~25 components explain ~90% variance

---

### Supervised learning

Models used:

- Support Vector Machine (SVM)
- Random Forest (RF)

Libraries:

sklearn.svm  
sklearn.ensemble  
sklearn.model_selection  
sklearn.metrics  

Training steps:

- Train/test split 80/20
- K-fold cross validation
- GridSearchCV hyperparameter tuning

Evaluation metrics:

- Confusion matrix
- Classification report
- ROC curve
- AUC score

---

## Results

SVM performance:

Accuracy = 88%  
F1 score (Control) = 0.86  
F1 score (HIV) = 0.90  
ROC AUC = 0.96  

Random Forest:

- Slightly lower accuracy
- Used for feature importance

---

## Feature Importance

Top genes identified by Random Forest:

- IFI27
- ARHGEF12
- TKTL1
- CHEK1
- ASPM
- FGF16
- AQR
- BNIP3

Gene annotation performed using mygene package.

---

## Output files

Generated figures:

- elbow_plot.png
- pca_plot.png
- dendrogram.png
- silhouette_plot.png
- confusion_matrix.png
- roc_curve.png
- feature_importance.png

All outputs saved in:

results/

---

## Project Structure

project/

data/  
Merged_HIV_Data_ML.csv  

scripts/  
preprocessing.py  
clustering.py  
pca.py  
svm_model.py  
rf_model.py  
feature_importance.py  

results/  

README.md

---

## Reproducibility

Run scripts in order:

python preprocessing.py  
python clustering.py  
python pca.py  
python svm_model.py  
python rf_model.py  

---

## Disclaimer

This project is for academic research purposes only.

---

## Author

Your Name  
MSc Bioinformatics / Computational Biology  
2025  
GitHub: https://github.com/yourusername
