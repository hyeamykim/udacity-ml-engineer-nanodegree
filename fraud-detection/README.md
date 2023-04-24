# Fraud Detection
In this project, SageMaker binary classifier was used to classify transaction data into fraudulent and non-fraudulent categories.

After a simple model was trained and tested, the model was tuned considering
1) Different evaluation metric than accuracy \
To decrease the number of false negatives and want a better recall value, train a binary classifier with 

> binary_classifier_model_selection_criteria='precision_at_target_recall', # target recall \
> target_recall=0.9) # 90% recall


2) Imbalanced training data, in which most data was non-fraudulent \
To account for class imbalance, train a binary classifier with 
> positive_example_weight_mult = 'balanced'

The credit card fraud data set from Kaggle was used. (https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

## Overvie of the Notebook
- Loading and exploring the data
- Splitting the data into train/test sets
- Defining and training a LinearLearner, binary classifier
- Making improvements on the model
- Evaluating and comparing model test performance
