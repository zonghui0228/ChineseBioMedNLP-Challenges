# CHIP 2020 CDN

## Task Introduction

Clinical terminology standardization is an essential task in medical statistics. In clinical practice, there can be hundreds or thousands of different expressions for the same diagnosis, surgery, medication, examination, test, symptom, etc. Standardization (normalization) aims to find the corresponding standard expression for the various expressions used in clinical practice. With the foundation of terminology standardization, researchers can proceed with statistical analysis of electronic medical records. Essentially, clinical terminology standardization is a form of semantic similarity matching task. However, due to the diverse ways in which terms are expressed, a single matching model often struggles to achieve good results.

## Task Details

The main objective of this evaluation task is to semantically standardize real diagnostic entities extracted from Chinese electronic medical records. Given an original diagnostic term, the task is to provide its corresponding standardized diagnostic term. All original diagnostic terms are derived from real medical data and have been annotated based on the "International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM) Beijing Clinical Edition v601" terminology. An example of annotation is provided below:


| 诊断原词                | 归一后的标准词（待预测值）        |
|-----------------------|-------------------------------|
| 右肺结节转移可能大       | 肺占位性病变##肺继发恶性肿瘤##转移性肿瘤 |
| 右肺结节住院           | 肺占位性病变                   |
| 左上肺胸膜下结节待查    | 胸膜占位                      |



## Evaluation Metrics

- The competition will use accuracy as the final evaluation metric. In this task, accuracy is defined as follows: the number of correct combinations of original diagnostic terms and standardized diagnostic terms divided by the total number of diagnostic terms to be predicted.

- For submission of the test set predictions, the following conventions are agreed upon:
  - File format: prediction.txt
  - Each line represents a record with the format: original term \t standardized term \n. Note that when there are multiple standardized terms, separate them with two hashtags (##), for example: standard term 1##standard term 2.
  - The order of the records should match the order of the test set.