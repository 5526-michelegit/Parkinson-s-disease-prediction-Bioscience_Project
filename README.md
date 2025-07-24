
# Integrated Data Science Workflow for Parkinson’s Disease Prediction

## Description
This project applies a comprehensive data science pipeline to Parkinson’s disease research, combining text mining of scientific literature, image‐based feature extraction from patient drawings, dimensionality reduction and visualization, and supervised machine learning models to predict disease severity.  

## Table of Contents
1. [Repository Structure](#repository-structure)  
2. [Requirements](#requirements)  
3. [Installation](#installation)  
4. [Usage](#usage)  
5. [Datasets](#datasets)  
6. [Objectives](#objectives)  
7. [Methodology](#methodology)  
   - [1. Literature Text Mining](#1-literature-text-mining)  
   - [2. Drawing Image Analysis](#2-drawing-image-analysis)  
   - [3. Dimensionality Reduction & Visualization](#3-dimensionality-reduction--visualization)  
   - [4. Model Development & Evaluation](#4-model-development--evaluation)  
8. [Tools & Libraries](#tools--libraries)  
9. [Achievements](#achievements)  
10. [Future Directions](#future-directions)   

## Repository Structure
```text
├── Parkinson_s_disease.ipynb   # Main notebook: data ingestion, text mining, feature extraction, model training & evaluation  
├── text_mining.ipynb           # Standalone notebook: detailed literature text mining and topic modeling  
├── Umap_visualization.ipynb    # Notebook: UMAP projection of drawing‐based features for exploratory visualization  
├── Bioscence_Presentation.pdf   # Slide deck summarizing objectives, methods, and key results  
└── README.md                   # This file  
```

## Requirements

* **Python 3.7+**
* **Jupyter Notebook**
* **Python libraries** (install via pip):

  * `numpy`
  * `pandas`
  * `scikit‑learn`
  * `matplotlib`
  * `seaborn`
  * `nltk`
  * `gensim`
  * `umap-learn`
  * `opencv-python`
  * `scikit-image`
  * `pillow`
  * `graycomatrix` (via `scikit-image`)

> It is recommended to use a virtual environment to isolate dependencies.

## Installation

1. **Clone** the repository:

   ```bash
   git clone https://github.com/5526-michelegit/Parkinson-s-disease-prediction-Bioscience_Project.git
   cd Parkinson-s-disease-prediction-Bioscience_Project
   ```
2. **Create** and activate a virtual environment (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate      # Linux / macOS
   venv\Scripts\activate.bat     # Windows
   ```
3. **Install** required packages:

   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn nltk gensim umap-learn opencv-python scikit-image pillow
   ```
4. **Download** NLTK resources (run once in Python or at the top of your notebook):

   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   nltk.download('wordnet')
   ```

## Usage

1. **Open** your Jupyter environment:

   ```bash
   jupyter notebook
   ```
2. **Run** the notebooks in order:

   * `text_mining.ipynb` to reproduce literature review and topic modeling.
   * `Umap_visualization.ipynb` to generate 2D projections of drawing‐based features.
   * `Parkinson_s_disease.ipynb` for end‑to‑end pipeline: feature extraction from images and text, model fitting, and evaluation.
3. **Review** the slides in `Bioscence_Presentation.pdf` for a high‑level overview of methods and results.

## Datasets

* **Literature Corpus**: 797 PubMed abstracts on patient drawing use in Parkinson’s research.
* **Drawing Images**: 51 spiral‐drawing scans from diagnosed patients, used for tremor severity feature extraction.

> *Note*: Raw data files are not included due to licensing; please obtain these from the project lead or relevant data repositories and adjust file paths accordingly in the notebooks.

## Objectives

* **Text Mining**: Identify prevailing research themes in Parkinson’s disease literature using tokenization, stop‑word removal, lemmatization, and topic modeling (LDA).
* **Image Analysis**: Preprocess and skeletonize spiral drawings to extract quantitative features (stroke thickness, endpoint/intersection counts, texture metrics via GLCM).
* **Visualization**: Apply UMAP for low‑dimensional embedding of drawing features to explore clustering patterns by severity.
* **Modeling**: Build and compare Logistic Regression, Ridge, and Lasso models to classify disease severity, evaluating performance via ROC curves and AUC.

## Methodology

### 1. Literature Text Mining

* **Data Acquisition**: Retrieve abstracts from PubMed based on keywords.
* **Preprocessing**: Clean text (lowercase, remove punctuation/numbers/stopwords), tokenize, form bigrams, lemmatize.
* **Topic Modeling**: Construct document–term matrix and fit an LDA model to extract latent themes.

### 2. Drawing Image Analysis

* **Enhancement**: Convert to grayscale, denoise, normalize contrast.
* **Skeletonization**: Thinning the drawing to a one‐pixel‐wide skeleton.
* **Feature Extraction**:

  * Stroke thickness statistics
  * Intersection and endpoint density
  * Texture descriptors using Gray‐Level Co‐Occurrence Matrix (contrast, homogeneity, entropy)

### 3. Dimensionality Reduction & Visualization

* **UMAP**: Reduce high‑dimensional drawing features to 2D for visualization.
* **Plotting**: Color‐code points by clinical severity score to assess natural groupings.

### 4. Model Development & Evaluation

* **Dataset Split**: Train/test partition (e.g., 70/30).
* **Algorithms**: Logistic Regression, Ridge Regression, Lasso Regression.
* **Metrics**: ROC curves, AUC, accuracy, precision, recall.
* **Validation**: Cross‐validation and bootstrapped confidence intervals for robust performance estimates.

## Tools & Libraries

* **numpy**, **pandas** for data handling
* **nltk**, **gensim** for text preprocessing and topic modeling
* **scikit‐image**, **opencv‐python** for image processing
* **scikit‐learn** for UMAP, modeling, and evaluation
* **matplotlib**, **seaborn** for plotting

## Achievements

* Conducted a systematic text mining of 797 Parkinson’s research articles to surface key thematic areas.
* Extracted quantitative drawing features linked to tremor severity and visualized cohort separations via UMAP.
* Developed and validated regression‐based classifiers achieving high AUC in severity prediction.

## Future Directions

* **Data Augmentation**: Increase drawing sample size via synthetic perturbations.
* **Advanced Models**: Explore tree‐based and neural network classifiers on combined text and image features.
* **Multimodal Fusion**: Integrate topic scores and drawing features in joint prediction frameworks.
* **External Validation**: Test models on independent patient cohorts from other clinics.
