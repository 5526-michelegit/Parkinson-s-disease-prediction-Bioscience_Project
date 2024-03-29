# Integrated Data Science Approach in Parkinson's Disease Analysis

Developed by Anna Maria Teodori, Ardalan Mehraram, and Michele Gazzola, this project aims to apply data science methodologies to analyze drawings and articles related to Parkinson's disease patients, providing insights into the disease's progression and severity.

## Project Overview

### Objectives
Our project focuses on:
- Evaluating literature on the usage of patient drawings as a metric of Parkinson's disease severity through text mining analysis.
- Exploring how Machine Learning (ML) models can aid in assessing disease severity based on these drawings.

### Methodology

#### Text Mining
We conducted a thorough literature analysis, collecting 797 articles from PubMed. The text mining process included data acquisition, preprocessing (removal of nulls, numbers, punctuation, stopwords, and application of tokenization, bigrams, lemmatization), and topic modeling to understand the prevailing themes in Parkinson's disease research.

#### Data Analysis of Drawings
We worked with a dataset comprising 51 images, focusing on features extraction from spiral drawings, a common method to visually rate tremor intensity. Our analysis included:
- Preprocessing for image enhancement.
- Skeletonization to visualize and analyze differences in drawing patterns.
- Extraction of multiple features such as stroke thickness, intersection and endpoint density, and texture analysis using the Gray-Level Co-Occurrence Matrix (GLCM).

### Model Development
We developed models to predict Parkinson's disease severity, employing Logistic Regression, Ridge Regression, and Lasso Regression. The models were evaluated using the ROC curve to determine their efficacy in classifying disease severity accurately.

## Tools and Libraries Used
- Python for data processing and modeling.
- Libraries such as NumPy, Pandas for data manipulation; Matplotlib, Seaborn for visualization; Scikit-learn for modeling.
- Text mining tools and techniques for literature analysis.

## Achievements
- Successfully applied text mining to Parkinson's disease literature to identify key research themes.
- Developed ML models capable of classifying Parkinson's disease severity with significant accuracy.
- Extracted and analyzed key features from patient drawings, contributing to our understanding of tremor intensity and disease progression.

## Future Directions
- Enhance model performance through data augmentation and hyperparameter optimization.
- Expand text mining and topic modeling to additional sources.
- Incorporate more diverse data sources for comprehensive analysis.

We thank all contributors and supporters of this project. For further details on our methodologies, findings, and future work, please refer to the full project documentation in this repository.
