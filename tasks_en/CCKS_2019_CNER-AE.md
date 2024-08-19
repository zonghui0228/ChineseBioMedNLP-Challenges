# CCKS 2019 CNER-AE


This task is a continuation of a series of evaluations conducted by CCKS around the semanticization of Chinese electronic medical records. Building on the foundation of the CCKS 2017 and 2018 medical named entity recognition evaluation tasks, it has been extended and expanded.

It includes two subtasks: 

- 1) Medical Named Entity Recognition: Due to the lack of publicly available datasets for medical entity recognition in Chinese electronic medical records, this year's evaluation retains the medical named entity recognition task. The dataset from 2017 has been revised and released along with the task. 

- 2) Medical Entity and Attribute Extraction (Inter-hospital Migration): Building upon medical entity recognition, predefined entity attributes are extracted. This task is a transfer learning task, meaning that with only a small amount of labeled data provided for the target scenario, the recognition task for the target scenario is performed using labeled data and unlabeled data from other scenarios.

Teams can choose to participate in both subtasks simultaneously or select either subtask for individual participation.

## Medical Named Entity Recognition

### Task Definition and Description

For a given set of electronic medical record plain text documents, the goal of the task is to identify and extract mentions of entities related to medical clinical contexts, and categorize them into predefined categories such as diseases, treatments, examinations, and tests.

#### Formal Definition

**Input:**

- A collection of natural language texts from electronic medical records.

- Predefined categories.

**Output:**

- A set of entity mentions paired with their corresponding categories.


#### Predefined Categories

The predefined categories are defined as follows:

- Symptoms and Signs: Symptoms are subjective feelings described by the patient, while signs are objective facts observed externally.

- Tests and Examinations: Provide clinical diagnostic and treatment evidence through laboratory techniques and medical equipment.

- Diseases and Diagnoses: Diseases are abnormal life processes that occur due to self-regulatory disorders caused by pathogenic damage under certain conditions; diagnoses involve identifying the disease a patient has based on symptoms.

- Treatments: Processes and activities that intervene or alter specific health conditions, such as medications, surgeries, etc.

- Body Parts: Anatomical locations in the human body where diseases, symptoms, and signs occur.

### Dataset Description

The dataset is provided by Beijing JIMU Cloud Health Technology Co., Ltd. and is derived from real electronic medical record data from their Cloud Hospital platform. It is exclusively for use in the CCKS competition evaluations.


### Evaluation Metrics

Precision, Recall, and F1-Measure are used as evaluation metrics. The evaluation is conducted separately for each of the five predefined categories to assess the performance in each subcategory.



## Medical Entity and Attribute Extraction (Inter-hospital Migration)

### Task Definition and Description

For a given set of electronic medical record plain text documents, a set of target fields related to medical information is defined, such as tumor size, primary tumor site, etc. The goal of the task is to identify and extract answer entities for these target fields, such as left lung, lobe of the lung, etc.

This task involves inter-hospital migration of entity and attribute extraction problems, meaning that with only a small amount of labeled data provided for the target scenario to be identified, a significant amount of labeled data with different known data distributions from other scenarios, as well as a large amount of unlabeled data, are provided for the recognition task in the target scenario.


#### Entity Category Definition

Considering the content and characteristics of the data source "Cancer Medical Imaging Examination and Conclusion," this task focuses on three main types of fields related to cancer: primary tumor site, lesion size, and metastatic sites. Each field in a text may contain multiple or zero target entities, such as multiple primary tumor sites.

- Primary Tumor Site: The tissue or organ where a disease first occurs, such as primary lung cancer in the upper lobe of the left lung.

- Lesion Size: The size of the primary tumor site, typically represented by the maximum diameter or size.

- Metastatic Sites: The tissues or organs to which a disease spreads from the initial tissue or organ where it first occurred.Entity Category Definition



### Dataset Description

The training data for this evaluation will be divided into three parts (specific quantities to be determined):

- 900 annotated data points from non-target scenarios.
- 100 annotated data points from the target scenario.
- 800 unlabeled data points from various scenarios.

Additionally, 200 annotated data points from the target scenario will be utilized as the test set for the final evaluation. A detailed description of the dataset will be provided alongside its release.

### Evaluation Metrics

Since each field in a text may contain multiple entities, the evaluation metrics will calculate precision and recall based on entities rather than fields, ultimately using the F1 score of entities as the evaluation metric.







