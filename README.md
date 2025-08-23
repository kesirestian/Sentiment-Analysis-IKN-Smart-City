# Aspect-Based Sentiment Analysis for Mapping Public Perception of Nusantara's Capital in Smart City Domains

This repository contains the official source code, data, and models for the manuscript: "Aspect-Based Sentiment Analysis for Mapping Public Perception of Nusantara's Capital in Smart City Domains," submitted to the 2025 12th International Conference on Electrical Engineering, Computer Science and Informatics (EECSI).

## Overview

This research performs Aspect-Based Sentiment Analysis (ABSA) to analyze public perception on Indonesia's new capital, Nusantara (IKN), using tweets from platform X. The study maps public sentiment across six smart city domains by comparing several models, including a TF-IDF+SVM baseline, and fine-tuned IndoBERT/IndoBERTweet in both pipeline and Multi-Task Learning (MTL) architectures. 

## Repository Structure

-   **/data**: Contains the datasets used for the experiments, including the labeled dataset for training and the larger preprocessed corpus for final analysis.
-   **/notebooks**: Contains all Jupyter Notebooks that document the entire research workflow in sequential order.
-   **/models**: Contains the saved, fine-tuned models from the experiments for reproducibility.
-   **/results**: Contains generated outputs such as performance charts, result tables, and visualizations presented in the paper.
-   `requirements.txt`: A list of all Python libraries required to run the code.

## Setup and Installation

1.  Clone this repository to your local machine:
    ```bash
    git clone [https://github.com/kesirestian/Sentiment-Analysis-IKN-Smart-City.git](https://github.com/kesirestian/Sentiment-Analysis-IKN-Smart-City.git)
    cd Sentiment-Analysis-IKN-Smart-City
    ```
2.  Install the required packages using pip:
    ```bash
    pip install -r requirements.txt
    ```

## How to Reproduce the Results

The experiments are organized sequentially in the `/notebooks` directory. Please run or review them in the following order to understand the complete research workflow.

1.  **`1_Data_Preprocessing.ipynb`**: Cleans the raw tweet data collected from platform X.
2.  **`2_Data_Preparation_KFold.ipynb`**: Prepares the cleaned and labeled dataset for 5-fold stratified cross-validation.
3.  **`3_Experiment_Baseline_SVM.ipynb`**: Trains and evaluates the baseline SVM model for aspect category detection.
4.  **Pipeline Models**: This section trains and evaluates the two-stage pipeline models (ACD followed by ASC).
    * `4_Experiment_Pipeline_IndoBERT_ACD.ipynb`
    * `5_Experiment_Pipeline_IndoBERT_ASC.ipynb`
    * `6_Experiment_Pipeline_IndoBERTweet_ACD.ipynb`
    * `7_Experiment_Pipeline_IndoBERTweet_ASC.ipynb`
5.  **Multi-Task Learning (MTL) Models**: This section trains and evaluates the MTL models which predict aspect and sentiment simultaneously.
    * `8_Experiment_MTL_IndoBERT.ipynb`
    * `9_Experiment_MTL_IndoBERTweet.ipynb`
6.  **`10_Results_Analysis.ipynb`**: Compares the performance (Macro F1-score) of all tested models to select the best-performing one.
7.  **`11_Error_Propagation_Analysis.ipynb`**: Conducts an error analysis on the chosen pipeline model to understand how errors from the first stage affect the second.
8.  **`12_Label_Prediction_and_Analysis.ipynb`**: Uses the best model (IndoBERTweet Pipeline) to predict labels for the entire unlabeled dataset and generates the final visualizations (e.g., word clouds, sentiment distribution charts) presented in the paper.

## Models

The fine-tuned model files are too large to be hosted directly on GitHub. You can download the best-performing model (IndoBERTweet Pipeline) from the following link:

[**Download Model from Google Drive**](https://bit.ly/indobertweet_pipeline_best_model)

After downloading, please extract the `.zip` file and place the contents into the `/models/pipeline_indobertweet/` directory to run the prediction notebooks.
