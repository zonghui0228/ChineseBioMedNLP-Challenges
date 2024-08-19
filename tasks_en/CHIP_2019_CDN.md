# CHIP 2019 CDN


## Task Description

Standardization of clinical terms is an essential task in medical statistics. In clinical practice, there are often hundreds or thousands of different ways to describe the same diagnosis, surgery, medication, examination, laboratory test, symptom, etc. The problem that standardization aims to solve is to find the corresponding standard terms for these various expressions in clinical settings. With the foundation of term standardization, researchers can proceed with statistical analysis of electronic medical records. Essentially, standardizing clinical terms is also a task of matching semantic similarity. However, due to the diverse ways in which original terms are expressed, it is difficult for a single matching model to achieve good results.

The main goal of this evaluation task is to semantically standardize real surgical entities extracted from Chinese electronic medical records. Given an original surgical term, the task is to provide its corresponding standard surgical term. All original surgical terms are sourced from real medical data and have been annotated according to the "ICD9-2017 Union Clinical Edition" surgical term list.


## Evaluation Metrics

The competition uses accuracy as the final evaluation metric. In this task, accuracy is defined as:
Number of correct combinations of original surgical terms with standard surgical terms / Total number of original surgical terms to be predicted


## Task Submission Guidelines

- The submission format should be consistent with the training data format, with the file extension .xlsx. When there are multiple values for standard terms, separate them with two hashtags (##), for example: Standard Term 1##Standard Term 2.

- The order of the data should be maintained the same as in the original file.

- This evaluation allows the use of public data resources and personal/organizational internal resources of the participants.

- Participants can perform various subtasks for this standardization task. For the test set (expected to be open by the end of October), participants are not allowed to perform any manual annotations.

