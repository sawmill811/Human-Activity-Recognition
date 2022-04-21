# Human-Activity-Recognition

## Introduction
This is my *bonus project* for the course <u>Pattern Recognition and Machine Learning (2022 Winter Semester)</u>. The problem statement is:<br>
*Human activity recognition is the problem of classifying sequences of data recorded by specialized harnesses or smartphones into known well-defined human activities. The goal of this machine learning project is to build a classification model that can precisely identify human fitness activities. Working on this machine learning project will help you understand how to solve multiclass-classification problems.*<br>

## Dataset
The Human Activity Recognition database was built from the recordings of 30 study participants performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors. The objective is to classify activities into one of the six activities performed:<br>
* Walking
* Walking Upstairs
* Walking Downstairs
* Sitting 
* Standing
* Laying

The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers were selected for generating the training data and 30% for the test data.<br>Each row consists of *561 features*, *1 label* `(Activity)` and one column denoting the *subject ID*. The dataset is available at [Kaggle](https://www.kaggle.com/datasets/uciml/human-activity-recognition-with-smartphones).<br>

## Pipeline
My task for this project was to implement an *end-to-end pipeline* that could take the dataset and output predictions for the test data along with some metrics to evaluate its performance. The pipeline consists of the following components:<br>
* **Importing Data**: Train and Test datasets can be input either as *URLs (relative or absolute)* or as `Pandas DataFrames`.
* **Preprocessing**: NULL values are removed from the dataset and the features are scaled using the *Scaler* chosen by the user `(StandardScaler/MinMaxScaler/MaxAbsScaler)`.
* **Training the Model**: Using the model parameters I found while exploring the task, the model is trained on the training data. I found `LinearDiscriminantAnalysis` and `XGBoostClassifier` to be the best performing models for this task, hence I have given the user the option to choose either one of these models.
* **Evaluation**: The model is evaluated on the test data and predictions are stored in the working directory under the filename `predictions.csv`. *Accuracy* on the test dataset along with a *classification report* containing different metrics is printed.

## Instructions for running the notebook
* Use `git clone https://github.com/sawmill811/Human-Activity-Recognition.git` in your terminal to clone the repository. If you wish to run the file on **Google Colaboratory**, then here is the [link to the notebook]().
* To run the pipeline, simply run the first cell in the `HAR.ipynb` notebook - this will import the necessary libraries.
* Next, skip all cells under the heading *"Exploring the Task"* and run the cells under the heading *"Creating a Pipeline"*. 
* The predictions for the test data will be stored in the working directory under the filename `predictions.csv`.