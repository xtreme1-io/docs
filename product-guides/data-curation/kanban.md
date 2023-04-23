---
description: >-
  A dataset kanban board is a great way to visualize the progress of your
  machine learning dataset through the different stages of its lifecycle.
---

# Kanban

## Scenario

Find it in `Dataset` -> `Scenario`

This page allows you to search your data in this dataset by search ontologies.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Display all data with the same class name</p></figcaption></figure>

## Spilt Dataset

When building a machine learning model, it is common to split your data into three subsets:

1. Training set: The majority of your data (typically 60-80%) that is used to train your model. Your model learns from the training data by finding patterns and correlations to understand the relationship between the input and output.
2. Validation set: A portion of your data (typically 10-20%) that is used to evaluate your model during training. After each epoch or iteration of training, you test your model on the validation set to check its performance. You then tweak or retrain your model as needed to improve validation accuracy.
3. Test set: A portion of your data (typically 10-20%) that is held out and not used during training at all. It is only used at the very end, to test your final trained model. Performance on the test set determines how well your model can generalize to new data.&#x20;

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

The split between training, validation and test sets is typically:

* Training set: 60-80% of your data
* Validation set: 10-20% of your data
* Test set: 10-20% of your data

## Dataset Overall

Find it in `Dataset` -> `Overall`, some statistics about the dataset can be seen:

* Total number of files;
* Total number of results;
* Data annotation progress
* Distribution histogram by `class` or `classification`

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
