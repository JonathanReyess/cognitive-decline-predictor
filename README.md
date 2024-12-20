
# Cognitive Decline Prediction Using EEG Data and Machine Learning

## Project Overview

The goal of this project is to develop a machine learning model that can predict cognitive decline based on patterns in electroencephalogram (EEG) data, which records brain activity. 

## Data Acquisition

This project utilizes the EEG dataset available on OpenNeuro. 

The dataset contains EEG resting state recordings from individuals diagnosed with Alzheimer's disease (AD), Frontotemporal Dementia (FTD), and healthy controls (CN).

To download this dataset, you can use the `@openneuro/cli` command-line tool. 

### Installation
First, ensure you have Node.js installed on your machine. You can download it from [nodejs.org](https://nodejs.org/).

Then, install the OpenNeuro CLI globally by running:
```bash
npm install -g @openneuro/cli
```

### Authentication

Before running the download command, you will need to log in to your OpenNeuro account to obtain an API key. Use the following command to log in:

```bash
openneuro login
```

### Downloading the Dataset 

To download the dataset, execute the following command in your terminal:

```bash
openneuro download --snapshot 1.0.7 ds004504 ds004504-download/
```

## Results

The performance of the model was evaluated using precision, recall, and F1-score metrics across the different classes. 

The following table summarizes the results:

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|--------|
| A (Alzheimer's Disease) | 0.67      | 0.75   | 0.71     | 8      |
| F (Frontotemporal Dementia) | 0.75      | 0.38   | 0.50     | 8      |
| C (Healthy Control) | 0.40      | 1.00   | 0.57     | 2      |

### Summary of Performance Metrics
- **Macro Average**:
  - Precision: 0.61
  - Recall: 0.71
  - F1-Score: 0.59

- **Weighted Average**:
  - Precision: 0.67
  - Recall: 0.61
  - F1-Score: 0.60

The overall accuracy of the model was **61%**. 

### Hyperparameter Tuning

To improve our model's performance, we tried hyperparameter tuning using Randomized Search. The goal being to find the best parameters to boost the model's accuracy. However, our dataset is too small, making it prone to overfitting.

To get a better idea of the model's performance, we used cross-fold validation by testing the model on different parts of the data. 

With cross-fold validation, the average accuracy increased from 61% to **65%**, which was a small improvement. 

Additionally, we achieved an ROC AUC score of **0.72**, showing that the model has a decent ability to distinguish between classes.

## Related Research

This project is built upon methodologies and insights presented in the research paper titled [“EEG Features for Cognitive Load Classification: A Systematic Review”](https://www.mdpi.com/2306-5729/8/6/95). 

The paper explores various EEG features and their effectiveness in cognitive load classification, providing a foundation for the feature selection and analysis conducted in this project. 

By leveraging the techniques outlined in this study, we aim to enhance our understanding of cognitive load through EEG signal processing.
