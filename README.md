# Reducing effort in logs reviews

Capstone project for **Udacity Machine Learning Engineer Nanodegree**.

![Logs Review](logs_review_pic.png)

## Notebooks
There are six notebooks used in this project:

Notebooks A: There is one notebook that shows data exploration, and two notebooks that shows hyperparameters tuning for clustering ML models:
1. [data_exploration_preprocessing.ipynb](data_exploration_preprocessing.ipynb)
2. [agglomerative_tuning.ipynb](agglomerative_tuning.ipynb)
3. [hdbscan_tuning.ipnyb](hdbscan_tuning.ipnyb)

Notebooks B: There are three main notebooks that shows the ML models being implemented in this project:
1. [linearLearner.ipynb](linear_learner/linearLearner.ipynb)
2. [clustering_agglomerative.ipynb](agglomerative_clustering/clustering_agglomerative.ipynb)
3. [clustering_hdbscan.ipynb](hdbscan_clustering/clustering_hdbscan.ipynb)

All notebooks are run in AWS Sagemaker environment.

## Installation
Most of the required libraries already exist in AWS Sagemaker environment.
To run the Jupyter notebooks (1-6) in AWS Sagemaker environment, use kernel conda_pytorch_p36

For notebooks A1, A2 and A3, the following additional libraries required to be installed:
- loglizer==1.0
- hdbscan==0.8.27

For notebook B1, there is no further installation required.

For notebook B2 and B3, there is no further installation required as containers are used. Required libraries are defined in Dockerfile and are installed during container build.

## Documentation
[Project Report](Project_Report.pdf)\
References to supporting material for the project are stated in footnotes at relevant sections of project report.

[Submission Notes](student_submission_notes/)
