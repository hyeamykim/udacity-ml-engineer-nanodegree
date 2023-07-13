# Capstone Project

## Traffic Flow Forecasting with Temporal Graph Convolutional Network (TGCN)

In this project, [Temporal Graph Convolutional Network](https://arxiv.org/pdf/1811.05320.pdf) (TGCN) was used for the problem of short-term traffic flow forecasting using both spatial and temporal information.

## Outline
- Problem Definition
- Dataset
- Methodology
- Dependencies
- Evaluation
- Demo
- References

### Problem Definition
Given the connectivity of sensor locations, traffic volume time series, and other features in neighboring locations, traffic flow prediction aims to predict the traffic volume for all sensor locations. Traffic volume is measured with the number of cars at each sensor location and was predicted for the next 15 minutes.

### Dataset
The [traffic flow forecasting dataset](https://archive.ics.uci.edu/dataset/608/traffic+flow+forecasting) from UCI Machine Learning Repository was used.
The dataset contains 47 features (10 previous time step traffic volume measurements, 7 one-hot-encoded weekday features, 24 one-hot-encoded hour-of-the-day features, 4 road direction features, number of lanes, and road name) for 36 sensor locations.
The dataset was divided into the train set and the test set, which contain 1261 and 840 instances, respectively. 
For this project, the train set was further divided into 80% train set and 20% validation set.

### Methodology
![T-GCN: A Temporal Graph Convolutional Network for Traffic Prediction](https://github.com/hyeamykim/udacity-ml-engineer-nanodegree/assets/39967211/c03aa0ae-748b-4a2f-baf8-f503920a40f0)

TGCN is utilizing both Graph Convolutional Network (GCN) and Gated Recurrent Unit (GRU) to learn both the spatial and temporal dependency of the dataset.
It takes a feature matrix, X, combined with the updated hidden state output of GRU, h, as inputs and updates them to create output with hidden dimensions, which can then be used as inputs for the regressor to produce the final output of traffic volume prediction.

TGCN was implemented in PyTorch and PyTorch-Lightning. The original code is from the official [TGCN GitHub repository](https://github.com/lehaifeng/T-GCN) and revised to fit the multivariate dataset for the project.

### Dependencies
PyTorch

PyTorch Lightning==2.04

### Evaluation
Following the metrics from the TGCN paper and the paper that published the traffic flow forecasting dataset, Root Mean Square Error (RMSE) was used to evaluate the forecasting performance of the model.

### Demo
The traffic_volume_forecasting_final.ipynb contains a code that lets you download the dataset, inspect it, change it to be used with PyTorch models, define and train the model, and inspect the training progress and forecasting results from the best epoch via tensorboard.

### References
- Dataset: https://archive.ics.uci.edu/dataset/608/traffic+flow+forecasting
- Paper that published the dataset: https://dl.acm.org/doi/pdf/10.1145/3339823
- TGCN paper: https://arxiv.org/pdf/1811.05320.pdf
- TGCN GitHub repository: https://github.com/lehaifeng/T-GCN
