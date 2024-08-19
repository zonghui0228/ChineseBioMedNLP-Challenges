# CHIP 2021 CDN


## Task Introduction

Standardizing clinical terms is an indispensable task in medical data analysis. In clinical practice, there are often hundreds or thousands of different ways of expressing the same diagnosis, procedure, medication, test, laboratory result, symptom, etc. The problem that standardization (normalization) aims to solve is to find the corresponding standard expressions for the various different expressions used in clinical practice. With the foundation of term standardization, researchers can proceed with subsequent statistical analysis of electronic medical records. Essentially, the task of standardizing clinical terms is also a type of semantic similarity matching task. However, due to the wide variety of original word expressions, a single matching model struggles to achieve good results.

## Task Details

The main goal of this evaluation task is to semantically standardize real diagnosis entities extracted from Chinese electronic medical records. Given the original diagnosis term, the task is to provide its corresponding standardized diagnosis term, annotated according to the "International Classification of Diseases ICD-10 Beijing Clinical Version v601."

In addition to the diagnostic standardization task from 2020, we are also providing a portion of surgical entities and their corresponding surgical standardization relationships corpus. It is expected that incorporating additional surgical standardization information will enhance the diagnostic standardization effectiveness.


## Annotation Example

| 诊断原词               | 归一后的标准词（待预测值）           |
|-----------------------|-----------------------------------|
| 右肺结节转移可能大     | 肺占位性病变##肺继发恶性肿瘤##转移性肿瘤 |
| 右肺结节住院          | 肺占位性病变                      |
| 左上肺胸膜下结节待查  | 胸膜占位                          |

| 手术原词                             | 手术标准词     |
|-------------------------------------|--------------|
| 右额叶病损切除术(神经导航+电生理)     | 额叶病损切除术 |
| 右颈部静脉瘤切除术                  | 颈部血管瘤切除术 |
| 眼睑肿物切除术                      | 去除眼睑病损   |


## Evaluation Metrics

The competition will use accuracy as the final evaluation metric. In this task, accuracy is defined as the number of correct combinations of original diagnosis terms and standardized diagnosis terms divided by the total number of original diagnosis terms to be predicted.

Submit the prediction results of the test set in a file named prediction.txt following the conventions below:

Each line represents a record in the format: original term \t standardized term \n. Note that when there are multiple values for the standardized term, separate them with two hashtags (##), for example: standard term 1##standard term 2.
Maintain the order of records consistent with the test set.