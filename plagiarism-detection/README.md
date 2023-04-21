# Plagiarism Detection

## Project Overview
The goal of this project was to build a plagiarism detector that examines a text file and performs binary classification; 
labeling that file as either plagiarized or not, depending on how similar the text file is to a provided source text.

This project has three main notebooks:

### Notebook 1: Data Exploration

To load in the corpus of plagiarism text data.\
To inspect the existing data features and the data distribution.

### Notebook 2: Feature Engineering

To clean and pre-process the text data.\
To define features for comparing the similarity of an answer text and a source text, and extract similarity features such as

- Ngrams:  a contiguous sequence of n items from a given sample of text or speech

- Containment: number of common ngrams divided by number of total ngrams given a pair of texts

![image](https://user-images.githubusercontent.com/39967211/233638353-997d213a-af5f-48ea-93e1-55ad4cd421c1.png)

- Longest Common Subsequence

To select "good" features, by analyzing the correlations between different features.\
To create train/test .csv files that hold the relevant features and class labels for train/test data points.

### Notebook 3: Train and Deploy the Model in SageMaker

To upload train/test feature data to S3.\
To define a binary classification model and a training script.\
To train the model and deploy it using SageMaker.\
To evaluate the deployed classifier.
