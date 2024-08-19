# CHIP 2023 DTC


## Task Introduction

With the rapid development of the internet, the demand for professional information on diabetes among a large number of type 2 diabetes patients and high-risk populations is becoming increasingly prominent. Diabetes, as a typical chronic disease, has become one of the major global public health challenges. Diabetes automatic question-answering services are playing an increasingly important role in the daily health services of patients and high-risk populations. The Chinese Diabetes Question Classification Evaluation Task aims to automatically classify diabetes-related questions raised by patients. This task will help enhance the performance of search results and promote the development of diabetes automatic question-answering services.

## Details of the Task

Participants are required to predict the categories corresponding to diabetes questions in the test set. After making predictions, they need to fill in the missing category label data in the test dataset. The evaluation phase will only analyze the errors in the filled data to determine the prediction performance score.

## Data Description

The evaluation dataset contains a total of 6 classes of Chinese diabetes questions, including diagnosis, treatment, common knowledge, healthy lifestyle, epidemiology, and others. The data is divided into training, validation, and test sets in a ratio of 6:1:1. There are a total of 6000 data points. The datasets are stored in .txt format. The training, validation, and test sets contain 'question' and 'label', while the classification dataset contains 'class' and 'label'.

| Category          | Training Set | Validation Set | Test Set | Total  |
|-------------------|--------------|----------------|----------|--------|
| Diagnosis         | 527          | 103            | 87       | 717    |
| Treatment         | 1501         | 260            | 265      | 2026   |
| Common Knowledge  | 1226         | 212            | 217      | 1655   |
| Healthy Lifestyle | 1702         | 251            | 273      | 2226   |
| Epidemiology      | 599          | 118            | 90       | 807    |
| Others            | 445          | 56             | 68       | 569    |
| Total             | 6000         | 1000           | 1000     | 8000   |

## Data Example

The training/validation set is as follows (the dataset does not store the headers 'question' and 'label').

| question                       | | label | 
|--------------------------|-------|-------|
| 糖尿病会引起眼睛水肿吗        | /t    | 4     |
| 糖尿病患者能用党参泡水喝吗    | /t    | 3     |
| 糖尿病人吃菠菜好吗            | /t    | 3     |
| 孕妇得了糖尿病怎么办        | /t    | 1     |

The classification dataset is as follows (the dataset does not store the headers 'class' and 'label'):

| class          |  | label | 
|--------------|----|-------|
| Diagnosis        | /t    | 0     |
| Treatment        | /t    | 1     |
| Common Knowledge | /t    | 2     |
| Healthy Lifestyle| /t    | 3     |
| Epidemiology     | /t    | 4     |
| Other            | /t    | 5     |


## Evaluation Method

### Evaluation Metric

This task employs accuracy (Acc) as the overall ranking criterion.

### Result Submission Format

Participants are requested to fill in the "label" column corresponding to the test set as per the following example. Use "\t" as the separator between "question" and "label" fields (do not store the "question" and "label" fields). Finally, save the file in the format pred.txt and submit it to the evaluation website.

|class		| | label |
|-|-|-|
| 糖尿病患者可以吃西瓜吗 |	/t |3 |












