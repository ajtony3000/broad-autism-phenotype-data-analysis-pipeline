# broad-autism-phenotype-data-analysis-pipeline
Project Description This project investigates the presence of Broad Autism Phenotype (BAP) traits in parents of children diagnosed with Autism Spectrum Disorder (ASD) and explores their correlation with the severity of ASD in children, as measured by CARS scores. The study utilizes the BAPQ (Broad Autism Phenotype Questionnaire) for parental assessment. The analysis includes normality testing, t-tests to compare parental BAPQ scores between parents of ASD children and typically developing children, chi-square tests for categorical associations, and logistic regression to model the relationship between parental traits and ASD severity. Furthermore, dimensionality reduction techniques (PCA, t-SNE) and various clustering algorithms (DBSCAN, K-Means, GMM, Hierarchical Clustering) are applied to identify potential subgroups within the parental data. Finally, a deep learning model is developed to predict autism based on BAPQ subscores, addressing class imbalance and providing interpretability through Grad-CAM visualizations. The project also explores the impact of engineered features and interaction terms on model performance.
Autism Spectrum Disorder (ASD) Parental Traits Analysis
Introduction
This repository contains the analysis for a study aimed at understanding the relationship between Broad Autism Phenotype (BAP) traits in parents and the severity of Autism Spectrum Disorder (ASD) in their children. We use the Broad Autism Phenotype Questionnaire (BAPQ) to assess parental traits and the Childhood Autism Rating Scale (CARS) to measure ASD severity in children.

The project covers a range of statistical and machine learning techniques, from normality testing and comparative analyses to dimensionality reduction, clustering, and deep learning for prediction.

Table of Contents
Installation
Dataset
Analysis Overview
Normality Testing
Comparative Analysis (T-tests & Chi-square)
Curve Fitting & Logistic Regression
Dimensionality Reduction (PCA & t-SNE)
Clustering (DBSCAN, K-Means, GMM, HAC)
Deep Learning Model
Results and Insights
Usage
Contributing
License
Installation
To run this analysis, you'll need Python 3.8+ and the following libraries. You can install them using pip:

pip install pandas numpy scipy scikit-learn matplotlib seaborn statsmodels tensorflow keras-tuner imbalanced-learn
Dataset
The dataset used in this study is BAPQ_Genderfile.xlsx. It contains parental BAPQ scores and CARS scores for children. The dataset is structured such that:

Rows 1-111 (index 0-110) typically represent parents of children with diagnosed ASD.
Rows 112-161 (index 111-160) typically represent parents of typically developing children.
Key columns include:

FINALSCOREf, Finalscore_M: Final BAPQ scores for father and mother.
Aloof_F, Aloof_M, Rigid_F, Rigid_M, Pragmaticlanguage_F, Pragmaticlanguage_M: BAPQ subscores for father and mother.
CARSscore: Childhood Autism Rating Scale score.
Analysis Overview
Normality Testing
Shapiro-Wilk tests are performed on various score distributions (original, sum, difference, product, and log-transformed versions) for the entire dataset and for the two subsets (ASD vs. non-ASD parents) to check for Gaussian distribution assumptions.

Comparative Analysis (T-tests & Chi-square)
Independent t-tests are conducted to identify significant differences in scores between the two parental subsets, with careful consideration for columns that failed normality tests. Chi-square tests are used to find optimal cutoffs for BAPQ scores that best differentiate between the subsets.

Curve Fitting & Logistic Regression
Linear and polynomial curve fitting are applied to explore the relationship between parental scores and CARS scores, particularly for severe ASD cases, after outlier removal. Binary logistic regression models are built to predict CARS severity (Mild-Moderate vs. Severe ASD) based on parental BAPQ scores.

Dimensionality Reduction (PCA & t-SNE)
Principal Component Analysis (PCA) and t-Distributed Stochastic Neighbor Embedding (t-SNE) are used to reduce the dimensionality of the BAPQ subscores, facilitating visualization and clustering.

Clustering (DBSCAN, K-Means, GMM, HAC)
Various clustering algorithms are applied to the PCA and t-SNE results to identify natural groupings or subgroups within the parental data based on their BAPQ profiles. DBSCAN, K-Means, Gaussian Mixture Models (GMM), and Hierarchical Agglomerative Clustering (HAC) are explored.

Deep Learning Model
A deep learning model is developed to predict autism (binary classification: ASD vs. non-ASD) using the six BAPQ subscores as input features. The model addresses class imbalance using SMOTE and employs a 75-5-20 train-validation-test split. Hyperparameter tuning is performed using Keras Tuner, and model interpretability is enhanced with Grad-CAM visualizations for misclassified samples.

Results and Insights
The notebook details the findings from each analysis step, including statistical significances, optimal cutoffs, cluster characteristics, and deep learning model performance metrics (loss, accuracy, classification report, confusion matrix).

Usage
To run the analysis:

Clone this repository.
Install the required Python packages.
Ensure the BAPQ_Genderfile.xlsx dataset is in the working directory or uploaded as prompted by the Colab notebook.
Execute the cells in the provided Jupyter Notebook (your_notebook_name.ipynb).
Contributing
Contributions are welcome! Please feel free to open issues or submit pull requests.
