# Patronizing language detection

This repository contains the codebase for our participation to **SemEval-2022 Task4, subtask 1 - Patronizing and Condescending Language Detection**. 
Submitted in partial fulfillment of the requirements for the Natural Language Processing (NLP) course of Imperial College London, in March 2022.

Authors: **Mathilde Outters**, **Elizabeth Bates**, **Venus Cheung**.


## Task
The overall goal of this project is to develop a binary classification model to predict whether a text contains patronising or condescending language.
More specifically, the coursework requires an implementation of a transformer-based model from Huggingface that outperforms the task’s RoBERTa-base baseline provided by the organisers in F1 score on the official dev dataset: **0.48**.

The official train and dev sets for this task are provided [here](https://github.com/Perez-AlmendrosC/dontpatronizeme/tree/master/semeval-2022/practice%20splits). 
The code to load the training data and generate predictions in the format expected by Codalab is taken from the [SemEval-2022 Task 4 repository](https://github.com/Perez-AlmendrosC/dontpatronizeme).

## Final predictions on the official test set

The model which performed the best on the dev set according to the various methods tried was a RoBERTa pretrained model, finetuned with a patronising/non-patronising data balance of 1:3 and having augmented both classes of the training data. 
We therefore used this model for our final predictions on the official test dataset. 

The predictions were submitted to CodaLab under the username **lb8s** and resulted in an F1 score of **0.551**.

## Report 
The report summarizes our findings with the following structure:
* Data analysis
* Modelling
  * Training on raw unbalanced dataset
  * Downsampling majority class and tuning class balance
  * Upsampling minority class and tuning class balance
  * Data Augmentation using synonym replacement
* Results analysis 
  * To what extent is the model better at predicting examples with a higher level of patronising content? 
  * How does the length of the input sequence impact the model performance? 
  * To what extent does the categorical data provided influence the model predictions?

