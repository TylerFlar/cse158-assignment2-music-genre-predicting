# cse158-assignment2-music-genre-predicting

## Table of Contents

- [cse158-assignment2-music-genre-predicting](#cse158-assignment2-music-genre-predicting)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Dataset](#dataset)
    - [Features Included:](#features-included)
  - [Project Structure](#project-structure)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Predictive Task and Evolution Framework](#predictive-task-and-evolution-framework)
  - [Model Design and Evaluation](#model-design-and-evaluation)
    - [Evaluation Metrics:](#evaluation-metrics)
    - [Hyperparameter Tuning:](#hyperparameter-tuning)
    - [Results](#results)
      - [Model Comparison](#model-comparison)
      - [Observations:](#observations)
  - [Acknowledgements](#acknowledgements)

## Introduction

This project aims to develop a machine learning model capable of classifying music tracks into their respective genres using a dataset with various audio features. 

## Dataset

- **Source:** [Kaggle - 10,400 Classic Hits](https://www.kaggle.com/datasets/thebumpkin/10400-classic-hits-10-genres-1923-to-2023)
- **Description:** The dataset comprises 15,150 music tracks from 3,083 artists, spanning from 1923 to 2023. Each track is annotated with a variety of audio features provided by Spotify and is classified into one of 19 genres.

### Features Included:
- **Track:** Title of the song.
- **Artist:** Name of the artist or band.
- **Year:** Release year of the track.
- **Duration:** Length of the track in milliseconds.
- **Time_Signature:** Musical time signature (e.g., 4/4).
- **Danceability:** Suitability for dancing (0.0 to 1.0).
- **Energy:** Intensity and activity (0.0 to 1.0).
- **Key:** Key the track is in (0=C).
- **Loudness:** Overall loudness in decibels (dB).
- **Mode:** Modality (0 = Minor, 1 = Major).
- **Speechiness:** Presence of spoken words (0.0 to 1.0).
- **Acousticness:** How acoustic the track is (0.0 to 1.0).
- **Instrumentalness:** Likelihood the track is instrumental (0.0 to 1.0).
- **Liveness:** Presence of a live audience (0.0 to 1.0).
- **Valence:** Musical positiveness (0.0 to 1.0).
- **Tempo:** Beats per minute (BPM).
- **Popularity:** Track's popularity (0 to 100).
- **Genre:** Genre label (19 unique genres). 

## Project Structure

```
cse158_assignment2_music_genre_predicting/
├── dataset-identification-and-exploratory-analysis.ipynb
├── predictive-task-and-evolution-framework.ipynb
├── model-design-and-evaluation.ipynb
├── data/
│   └── ClassicHit.csv
├── pyproject.toml
└── README.md
```

- **dataset-identification-and-exploratory-analysis.ipynb:** Conducts initial data exploration and analysis to understand dataset characteristics and feature distributions.
- **predictive-task-and-evolution-framework.ipynb:** Defines the predictive modeling task, including data preprocessing, baseline model establishment, and initial evaluations.
- **model-design-and-evaluation.ipynb:** Develops, tunes, and evaluates various machine learning models for genre classification, including ensemble methods.
- **data/**: Contains the dataset used for analysis and modeling.
- **pyproject.toml:** Manages project dependencies and configurations using Poetry.
- **README.md:** Provides an overview and documentation of the project.

## Exploratory Data Analysis

The initial analysis involves:

- **Data Loading & Cleaning:** Importing the dataset, checking for missing values, and removing duplicates.
- **Statistical Summary:** Generating descriptive statistics for numerical features.
- **Visualization:**
  - **Genre Distribution:** Bar charts highlighting class imbalances.
  - **Correlation Matrix:** Heatmap showing relationships between audio features.
  - **Feature Distributions:** Histograms for understanding feature distributions.
  - **Boxplots by Genre:** Visualizing feature variations across different genres.
  - **Temporal Analysis:** Trends of track releases and audio features over years.
  - **Pairplot:** Exploring pairwise relationships between features.
- **Data Encoding:** Converting categorical variables to suitable formats for modeling.

## Predictive Task and Evolution Framework
The core of the project focuses on building a genre classification model:

- **Target Variable:** Genre
- **Features:** Numerical audio descriptors like `Danceability`, `Energy`, `Loudness`, etc.
- **Baseline Model:** Establishing performance expectations using a `DummyClassifier`.
- **Data Preprocessing:**
  - **Encoding:** Label encoding for the target variable.
  - **Scaling:** Standardizing features to ensure uniformity.
  - **Handling Class Imbalance:** Utilizing SMOTETomek to balance the dataset.'

## Model Design and Evaluation

Multiple machine learning models are trained and evaluated, including:

- **Random Forest Classifier**
- **Support Vector Machines (SVM)**
- **XGBoost Classifier**
- **K-Nearest Neighbors (KNN)**
- **Extra Trees Classifier**
- **CatBoost Classifier**
- **Logistic Regression**
- **Multi-Layer Perceptron (MLP)**
- **Quadratic Discriminant Analysis (QDA)**
- **Voting Classifier (Ensemble Method)**

### Evaluation Metrics:
- **Accuracy Score**
- **Classification Report:** Precision, Recall, F1-Score
- **Confusion Matrix**

### Hyperparameter Tuning:
Implemented using GridSearchCV for models like Random Forest, XGBoost, Extra Trees, CatBoost, and MLP to optimize performance.

### Results

#### Model Comparison

| Model | Accuracy |
| ----- | -------- |
| DummyClassifier | 0.0635 |
| Random Forest | 0.3731 |
| SVM | 0.3240 |
| XGBoost | 0.3509 |
| KNN | 0.2531 |
| Extra Trees | 0.3489 |
| CatBoost | 0.3519 |
| Logistic Regression | 0.2679 |
| MLP | 0.3018 |
| QDA | 0.2524 |
| Voting Classifier | 0.3765 |

#### Observations:
- The **Voting Classifier** achieved the highest accuracy, outperforming individual models by leveraging their combined strengths.
- **Random Forest** and **XGBoost** also demonstrated strong performance, indicating their effectiveness in handling the classification task.
- The **DummyClassifier** performed significantly lower, validating the effectiveness of the implemented models.

## Acknowledgements

- **Spotify** for providing rich audio features.
- **Kaggle** for hosting the dataset.
- **Scikit-learn**, **XGBoost**, **CatBoost** communities for their machine learning libraries.
