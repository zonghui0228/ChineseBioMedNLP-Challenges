# CCKS 2017 CNER

## 1. Task Definition and Description

This evaluation task focuses on Clinical Named Entity Recognition (CNER), which is aimed at electronic medical records. For a given set of electronic medical record documents (plain text files), the goal of the task is to identify and extract entity mentions related to medical clinical practices and classify them into predefined categories such as diseases, symptoms, examinations, etc.

This year's evaluation task is a continuation of the CCKS 2016 entity discovery and entity linking evaluation in the film and television domain. The purpose is to promote research and development in the field of limited-domain entity recognition and entity linking. This evaluation is jointly organized by the Knowledge Engineering Laboratory of Tsinghua University, Microsoft Research Asia, and Beijing JIMU Cloud Health Technology Co., Ltd.


### 1.1 Input and Output

**Input:**

The input for the task consists of a set of electronic medical record data. A medical record refers to the original record of a patient's entire diagnosis and treatment process in a hospital, including admission records, progress notes, examination results, medical orders, surgical records, nursing records, etc. Considering the characteristics of the CNER task, the original electronic medical record data has been trimmed and organized, with a focus on extracting progress notes and examination results, stored in plain text format. Each entry represents a single visit record for a patient.

**Output:**

The output of the task includes:
- Entity mentions related to medicine found in the given document (string boundaries).
- The category corresponding to each entity mention.


### 1.2 Entity Category Definitions

For this evaluation, named entities are categorized into the following 5 classes:

- Symptoms and Signs: Symptoms are subjective feelings described by patients, while signs are objective facts observed externally. For example, a runny nose, dizziness, and a body temperature exceeding 38 degrees Celsius are elements of a cold. Runny nose and dizziness are symptoms of a cold, while a body temperature exceeding 38 degrees is a sign of a cold.

- Tests and Examinations: Refers to the basis provided for clinical diagnosis and treatment through laboratory techniques and medical equipment.

- Diseases and Diagnoses: Diseases are abnormal life processes that occur in the body under certain conditions due to damage from pathological factors, resulting in disturbances in self-regulation. Diagnosis refers to identifying the disease a patient is suffering from based on symptoms.

- Treatment: Typically involves the process of intervening or changing a specific health condition. Activities conducted to relieve illness, such as medication or surgery.

- Body Parts: Refers to the anatomical parts of the human body where diseases, symptoms, and signs occur.

## 2. Dataset Description

The dataset used for this task is provided by Beijing JIMU Cloud Health Technology Co., Ltd. The data is sourced from real electronic medical record data from their Cloud Hospital platform, totaling 800 entries (single visit records for individual patients). The data has undergone de-identification processing and is solely intended for evaluation in the CCKS 2017 competition.


### 2.1 Training Dataset:

The electronic medical record data is organized into four folders: General Information, Medical History, Diagnosis and Treatment Process, and Discharge Summary.
Each directory contains text data (.txtoriginal.txt) and corresponding annotated result data (.txt), with a one-to-one correspondence through the file names. For example, "General Information-1.txt" corresponds to "General Information-1.txtoriginal.txt."
The annotated result files contain the following 4 fields, separated by tabs:
- mention (entity name)
- pos_b (starting position of the entity name in the original text)
- pos_e (ending position of the entity name in the original text)
- category (category to which the entity belongs)

### 2.2 Test Dataset:

The data format is identical to the training dataset. Participants are required to provide annotated results that match exactly with the annotations in the training dataset. Any discrepancies due to formatting issues will not be scored.

### 2.3 Unlabeled Dataset:

This task will provide an unlabeled dataset consisting of 800-2000 records, serving as supplemental data for participants to engage in unsupervised or semi-supervised learning approaches.

## Evaluation Metrics:

In this task, the evaluation will be based on precision, recall, and F1-Measure as the metrics to assess the performance of the named entity recognition system.