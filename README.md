# Reducing effort in logs reviews

Capstone project for **Udacity Machine Learning Engineer Nanodegree**.

There are six notebooks used in this project:

There are one notebook that perform data exploration:
1) data_exploration_preprocessing.ipynb  

There are two notebooks that involves hyperparameters tuning for clustering ML models implemented in this project:
2) agglomerative_tuning.ipnyb
3) hdbscan_tuning.ipnyb

There are three main notebooks that runs the ML models implemented in this project:
4) linearLearner.ipynb (in folder linear_learner)
5) clustering_agglomerative.ipynb (in folder agglomerative_clustering)
6) clustering_hdbscan.ipynb (in folder hdbscan_clustering)

All notebooks are run in AWS Sagemaker environment.

## Installation
To run the Jupyter notebooks (1-6) and python scripts in AWS Sagemaker environment, use kernel conda_pytorch_p36

The following additional libraries required are required for notebooks 1-3:
- loglizer==1.0
- hdbscan==0.8.27

For notebook 4, there is no further installation required.

For notebook 5,6, there is no further installation required as containers are used. Required libraries is defined in Dockerfile and installed during container build.

## Documentation
[Project Report](Project_Report.pdf)
# MLEngr_Capstone_Proj
