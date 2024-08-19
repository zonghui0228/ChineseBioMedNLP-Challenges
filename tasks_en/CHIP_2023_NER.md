# CHIP 2023 NER


## Task Overview

Chinese medical named entity recognition is a fundamental task for achieving intelligent healthcare, extracting a vast amount of information on diseases, symptoms, and treatments embedded in texts. Currently, deep learning techniques have made significant progress in this task; however, data in the medical field is often difficult to obtain, which fails to meet the requirements of domain transfer and model training. Small sample learning is more in line with real-world applications, focusing on how to maintain high accuracy with a small amount of annotated data and possess good generalization ability.

## Task Details

The Chinese Medical Text Few-Shot Entity Recognition Dataset (CMFD) contains 15 labels: item, sociology, disease, etiology, body, age, adjuvant, therapy, electroencephalogram, equipment, drug, procedure, treatment, microorganism, department, epidemiology, symptom, and others (a category not belonging to any entity type). The dataset takes into account the problem of long-tail distribution of entity types. Few-shot learning is a special case of machine learning that limits the amount of training data for the target task. For the N-way-K-shot named entity recognition task (N=5, K=1 or 5), each data point includes N types, with each type having at least K instances, forming the support set for training, along with a corresponding query set for testing.

## Data Description

This evaluation task integrates medical data from multiple sources, covering pediatric diseases, obstetrics and gynecology, cardiovascular diseases, as well as major diseases such as lung cancer, liver cancer, and breast cancer. Two few-shot settings are provided (5-way-1-shot and 5-way-5-shot), each containing 600 data points. Under each setting, every data point comprises five types, sampled according to category distribution to ensure that each category has at least one example in the training set. The data is divided into training, validation, and test sets in a ratio of 4:1:1. Each data point is stored in JSON format and includes two subsets: support and query, consisting of several medical sentences where entity labels in the sentences are in sequential tagging format. Details can be seen in the table below.


| | Dataset  | Data (Count)      | Sentences (Count)      | Types                   |
|---------|--------------|--------------|---------------|-------------------------------------------|
| 5w1s    | train_data   | 400           | 2960| 'ite', 'soc', 'tre', 'bod', 'sym', 'dis', 'dep', 'dru' |
|         | dev_data     | 100           | 964| 'eti', 'EEG', 'age', 'adj', 'equ', 'mic', 'epi', 'dep' |
|         | test_data    | 100           | 946| 'eti', 'EEG', 'age', 'adj', 'equ', 'mic', 'epi', 'dep' |
| 5w5s    | train_data   | 400           | 14224| 'ite', 'soc', 'tre', 'bod', 'sym', 'dis', 'dep', 'dru' |
|         | dev_data     | 100           | 4707| 'eti', 'EEG', 'age', 'adj', 'equ', 'mic', 'epi', 'dep' |
|         | test_data    | 100           | 4707| 'eti', 'EEG', 'age', 'adj', 'equ', 'mic', 'epi', 'dep' |

## Data Example（5-way-1-shot）
```json
  { "support": { "sentences": ["镜下血尿发生率为 49.8%～86.7%，一般 24～48 小时后消失。", "（2）布地奈德（budesonide，BUD）：普米克都保或pMDI、英福美；BUD比BDP有较高的受体亲和性和水溶性，而与BMP接近。", " 痰培养、血培养可明确病原。", "患儿由于负氮平衡会导致肌无力和疲劳加重，尤其是婴儿。"], "labels": [ ["equ", "O", "sym", "sym", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O"], ["O", "O", "O", "dru", "dru", "dru", "dru", "O", "dru", "dru", "dru", "dru", "dru", "dru", "dru", "dru", "dru", "dru", "O", "dru", "dru", "dru", "O", "O", "dru", "dru", "dru", "dru", "dru", "O", "dru", "dru", "dru", "dru", "O", "dru", "dru", "dru", "O", "dru", "dru", "dru", "O", "dru", "dru", "dru", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "dru", "dru", "dru", "O", "O", "O"], ["ite", "ite", "ite", "O", "ite", "ite", "ite", "O", "O", "O", "O", "O", "O"], ["O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O", "dis", "dis", "dis", "O", "sym", "sym", "O", "O", "O", "O", "O", "O", "O", "O", "O"] ] }, "query": { "sentences": [ "可通过高通气降低血二氧化碳分压或（和）应用碳酸氢钠液体提高血pH，但两者的意义不同。", "ISKDC4a指50%以上肾小球受累。", "还原糖检查可用改良斑氏试剂或nitest试纸比色。"], "labels": [ ["O", "O", "O", "O", "O", "O", "O", "O", "ite", "ite", "ite", "ite", "ite", "ite", "ite", "O", "O", "O", "O", "O", "O", "dru", "dru", "dru", "dru", "O", "O", "O", "O", "ite", "ite", "ite", "O", "O", "O", "O", "O", "O", "O", "O", "O", "O"], ["dis", "dis", "dis", "dis", "dis", "dis", "dis", "O", "O", "O", "O", "O", "O", "sym", "sym", "sym", "sym", "sym", "O"], ["O", "O", "O", "O", "O", "O", "O", "O", "O", "dru", "dru", "dru", "dru", "O", "equ", "equ", "equ", "equ", "equ", "equ", "equ", "equ", "O", "O", "O"] ]}, "types": ["sym", "equ", "dru", "dis", "ite"]}
```

## Data Format Description

- "support": Contains sentences and their corresponding labels from the support set.

- "query": Contains sentences and their corresponding labels from the query set.

- "sentences": A list containing several sentences.

- "labels": A two-dimensional array where the elements of the first dimension are lists. The data in the second dimension correspond to abbreviations of the labels for each character in the sentences. Note: This item is an empty list in the test set.

- "types": The five entity categories in this data entry.

## Evaluation Method

### Evaluation Metrics:

Precision, recall, and F1-measure micro-average values.

### Submission Format:
You need to submit two files for 5w1s and 5w5s, containing the predicted labels of the query set generated by the model in JSON format, following the same data structure as the data samples. Name the two files as "5w1s_pred.json" and "5w5s_pred.json" respectively.





