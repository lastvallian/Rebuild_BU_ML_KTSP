# Rebuild_BU_ML_KTSP
Rebuild the KTSP Machine Learning 
Gene Expression Classification Pipeline

This repository implements a Hierarchical Classifier (HC) combined with the K-Top Scoring Pairs (K-TSP) algorithm for gene expression–based classification.
The pipeline follows a modular, step-by-step design aligned with bioinformatics and machine learning best practices.
Overview

The goal of this project is to:

Identify discriminative gene pairs using K-TSP

Construct a hierarchical classifier using these gene pairs

Evaluate classification performance using accuracy, confusion matrix, ROC curve, and heatmap visualization

Model Training Pipeline

The K-TSP Model Training Process consists of 8 clearly defined steps, each implemented as an independent module.

🔹 Step 1: Load, Normalize, and Detect Labels

Goal
Load the gene expression dataset, normalize the data, and detect class labels.

Actions

Load gene expression matrix

🔹Step 2: Convert Labels to Integer Classes

Goal
Convert categorical labels into integer-encoded classes for model training.

Actions

Encode string labels into integer classes

🔹 Step 3: Split Data into Training and Testing Sets

Goal
Split the dataset into training and testing subsets.

Actions

Stratified split to preserve class distribution


🔹 Step 4: Select Top K Variable Genes

Goal
Reduce dimensionality by selecting the most variable genes.

Actions

Compute gene-wise variance on training data

Select top K genes (default: 300)



🔹 Step 5: Score Top K Gene Pairs (K-TSP)

Goal
Identify the most discriminative gene pairs using the K-TSP algorithm.

Actions

Evaluate all gene pairs from selected genes

Score pairs based on relative expression ordering

Select top K scoring pairs


🔹 Step 6: Train Hierarchical Classifier with K-TSP

Goal
Construct a hierarchical classification tree using K-TSP classifiers at each node.

Actions

Build recursive HC tree

Train K-TSP classifier at each node


🔹 Step 7: Predict Test Data

Goal
Predict class labels for the test dataset.

Actions

Traverse the hierarchical tree

Aggregate predictions and decision scores

🔹 Step 8: Evaluate and Visualize Results

Goal
Evaluate model performance and visualize results.

Metrics

Accuracy

Confusion Matrix

ROC Curve (binary classification)

Gene Expression Heatmap

Normalize expression values

Detect whether labels exist in the first row
