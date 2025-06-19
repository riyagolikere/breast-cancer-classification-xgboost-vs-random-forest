
# Breast Cancer Classification: XGBoost vs. Random Forest

A comprehensive comparative analysis of XGBoost and Random Forest algorithms for distinguishing breast cancer tissue from normal tissue using TCGA gene expression data.



## Project Overview

This project aims to classify breast cancer samples as Primary Tumor or Solid Tissue Normal using gene expression data from the TCGA BRCA (Breast Invasive Carcinoma) dataset. Two powerful machine learning algorithms—XGBoost and Random Forest—are implemented and compared to determine which performs better in predicting cancerous vs. non-cancerous tissue.

Gene expression data contains high-dimensional features (~60,000 genes), and tree-based ensemble models are particularly suited for such tasks due to their ability to handle non-linearity, interactions between variables, and robustness to irrelevant features.


## Machine Learning Models

1. Random Forest:
Random Forest is an ensemble of decision trees trained using bagging (bootstrap aggregating). Each tree is trained on a different subset of the data and features. The final prediction is made by majority voting (classification). This reduces variance and improves generalization.

2. XGBoost (Extreme Gradient Boosting):
XGBoost is a boosting algorithm that builds trees sequentially, where each new tree corrects the errors of the previous ones. It uses gradient descent optimization, regularization, and early stopping to prevent overfitting.
## SHAP & Feature Importance
To understand which genes influenced the predictions, we used:

1. SHAP (SHapley Additive exPlanations): Provides local and global interpretability by quantifying each gene's contribution to individual predictions.

2. Feature Importance Plots: Derived from both Random Forest and XGBoost to highlight top predictive features (genes).


## Dimensionality Reduction
1. UMAP (Uniform Manifold Approximation and Projection):
We used UMAP to visualize high-dimensional gene expression data in 2D space, showing separation between tumor and normal samples.

##  Steps to Run

Step 1. Download the files and upload the notebook + datasets to Google Colab or Jupyter Notebook.

Step 2. Install dependencies (xgboost, scikit-learn, shap, umap-learn, pandas, matplotlib, seaborn)

```bash
  pip install xgboost scikit-learn shap umap-learn pandas matplotlib seaborn
```
Step 3. Run the notebook to:
- Load and preprocess data
- Train XGBoost and Random Forest
- Visualize SHAP values and UMAP embeddings
- Evaluate and compare models


## Data Sources

The data utilized in the analysis was obtained from:
1. [GDC TCGA Breast Cancer (BRCA)](https://xenabrowser.net/datapages/?dataset=TCGA-BRCA.star_counts.tsv&host=https%3A%2F%2Fgdc.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443)

This dataset contains gene expression profiles for 1,226 breast cancer samples from The Cancer Genome Atlas (TCGA), processed via the GDC STAR pipeline, available via the [UCSC Xena GDC hub](https://gdc.xenahubs.net).



2. [TCGA Breast Cancer (BRCA)](https://xenabrowser.net/datapages/?dataset=TCGA-BRCA.star_counts.tsv&host=https%3A%2F%2Fgdc.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443) 
[Dataset: phenotype - Phenotypes]
This clinical dataset includes phenotype metadata for 1,247 breast cancer cases, covering sample types (e.g., Primary Tumor, Solid Tissue Normal), ER/PR/HER2 status, and staging information, accessed from the [UCSC Xena TCGA hub](https://tcga.xenahubs.net
).

Source: TCGA-BRCA via UCSC Xena