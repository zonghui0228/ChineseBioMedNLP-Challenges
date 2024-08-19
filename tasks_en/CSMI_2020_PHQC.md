# CSMI 2020 PHQC


## Competition Background

With the development of health and medical informatization and the widespread application of technologies such as cloud computing, the Internet of Things, and mobile intelligence in the healthcare field, a massive amount of datasets have been generated in the processes of medical services, health care, and health management, forming medical big data. Medical data mining algorithms are important technical means for leveraging the value of medical big data. In order to better support intelligent medical information systems with data mining algorithms, the Medical Informatics Branch of the Chinese Medical Association has organized a medical data mining evaluation activity to assess the accuracy and adaptability of algorithms in specific medical application scenarios.


## Competition Topic Description

Based on provided Chinese health-related queries, the goal is to classify the topics of the queries (which include 6 major categories: A - Diagnosis, B - Treatment, C - Anatomy/Physiology, D - Epidemiology, E - Healthy Lifestyle, F - Choosing Doctors). Since a single Chinese health query often belongs to multiple topic categories, this automated classification task is a multi-label classification problem. The performance of participating teams will be measured by the F1-score of the algorithms constructed on the test set during the evaluation.


## Data Description

Training Set: A total of 5,000 Chinese health-related question data entries, formatted as follows:

| Field Name | Data Type | Description | Category Meaning                                                        |
|---|---|---|---|
| ID | string | Unique identifier for the data | N/A |
| Question Sentence | string    | Content of the question | N/A |
| category_A (Diagnosis)      | int       | 0 or 1, 0 indicates not belonging to this category, 1 indicates belonging to this category | Questions related to diagnosis, including inquiries about the etiology or clinical findings explanation, disease diagnostic criteria or clinical manifestations, laboratory tests, disease or condition introductions, etc. |
| category_B (Treatment)      | int       | 0 or 1, 0 indicates not belonging to this category, 1 indicates belonging to this category | Questions related to treatment, including inquiries about drug usage and dosage, drug selection, indications and efficacy, drug side effects and adverse reactions, contraindications and precautions, drug interactions, and other treatment methods. |
| category_C (Anatomy/Physiology) | int     | 0 or 1, 0 indicates not belonging to this category, 1 indicates belonging to this category | Questions related to anatomy/physiology, including inquiries about human body tissues and organs, human metabolism, etc. |
| category_D (Epidemiology)   | int       | 0 or 1, 0 indicates not belonging to this category, 1 indicates belonging to this category | Questions related to epidemiology, including inquiries about disease prevalence or incidence, etiology, pathogenesis, disease impact, disease progression, prognosis/complications, sequelae, etc. |
| category_E (Healthy Lifestyle) | int     | 0 or 1, 0 indicates not belonging to this category, 1 indicates belonging to this category | Questions related to healthy lifestyle, including diet, exercise, weight loss, stress and emotion management, etc. |
| category_F (Choosing Doctors)| int      | 0 or 1, 0 indicates not belonging to this category, 1 indicates belonging to this category | Questions related to choosing doctors, including inquiries about selecting medical institutions, medical departments, doctors, etc. |


## Data Example

| Field Name               | Field Example                                                                                                                                               |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                       | QC0000000012                                                                                                                                                 |
| Question Sentence        | Total cholesterol 7.38, what level does it belong to? Medical history (onset time, main symptoms, symptom changes, etc.): 1-2 years history, with mild cerebral infarction. Age 67. Thank you. Taking rosuvastatin, one tablet every other day. Is it okay? |
| category_A (Diagnosis)   | 1                                                                                                                                                           |
| category_B (Treatment)   | 1                                                                                                                                                           |
| category_C (Anatomy/Physiology) | 0                                                                                                                                                       |
| category_D (Epidemiology) | 0                                                                                                                                                           |
| category_E (Healthy Lifestyle) | 0                                                                                                                                                           |
| category_F (Choosing Doctors)  | 0                                                                                                                                                           |

## Data Download

| Data Name | Data Description |
|------------------|----------------------------------------------------------------|
| Training Set | Contains 5,000 Chinese health-related question data and corresponding classification results |
| Test Set | Contains 3,000 Chinese health-related question data |
| Submission Sample| "sample_submission.csv": Sample submission file with random results for reference by participants |

## Evaluation Metric

The commonly used F1-score in multi-label classification tasks will be adopted.

