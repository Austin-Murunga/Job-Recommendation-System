# Job Recommendation System

<img width="800" alt="image" src="https://github.com/user-attachments/assets/d776baee-6d54-490d-9dd2-2ff8cf58015d">



## Overview

This project is focused on building a **Job Recommendation System** that suggests job listings to users based on a given job title. It leverages content-based filtering, utilizing the **TF-IDF Vectorizer** and **K-Nearest Neighbors** algorithm to compute recommendations by measuring the similarity between job descriptions.

## Dataset

The dataset used in this project is the **Combined Jobs Final** dataset sourced from [Kaggle](https://www.kaggle.com/datasets/kandij/job-recommendation-datasets), which contains various job listings including details such as job title, company, location, job description, and more.

- **Rows**: 84,090
- **Columns**: 23

### Main Columns
- `Job.ID`: Unique identifier for each job listing.
- `Title`: Job title or role.
- `Company`: Name of the hiring company.
- `City`: City where the job is located.
- `State.Name`: Name of the state where the job is located.
- `Industry`: Industry related to the job.
- `Job.Description`: Detailed description of the job role.
- `Requirements`: Qualifications and skills required.
- `Salary`: Salary offered for the position.
- `Employment.Type`: Type of employment (e.g., full-time, part-time).

## Project Workflow

### 1. Business and Data Understanding

The project aims to help users find relevant job listings by providing recommendations based on job title similarity. The dataset was selected because it contains sufficient descriptive details to calculate textual similarities.

### 2. Data Preparation

- **Data Cleaning**: Missing values were removed from key columns such as `Title` and `Job Description`.
- **Text Preprocessing**: The `Job Description` field was processed to remove stop words, and the text was converted to a numerical format using **TF-IDF Vectorization**.

### 3. Modeling

The recommendation system was built using the **K-Nearest Neighbors (KNN)** algorithm with a **cosine similarity** metric to find job listings similar to a given input job title. The similarity is calculated based on the **TF-IDF** representation of the job descriptions.

- **Precision**: 1.0
- **Recall**: 0.0847
- The system provides highly relevant recommendations but could improve its recall, indicating it misses some relevant jobs.

### 4. Model Hypertuning

To improve the model’s performance, manual hyperparameter tuning was applied:
- Best parameters: `{'n_neighbors': 5, 'metric': 'cosine'}`.

## Dependencies

- Python 3.8+
- Pandas
- Scikit-Learn
- Numpy
- NLTK
- Matplotlib (for visualizations)

## Usage

The system allows users to input a job title, and it returns job listings that are most similar based on the job description. The recommendation is done by calculating the cosine similarity between job descriptions.

## Evaluation

- **Precision**: 1.0 (perfectly relevant recommendations).
- **Recall**: 0.0847 (low coverage of all relevant jobs).
