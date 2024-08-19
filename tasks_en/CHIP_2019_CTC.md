# CHIP 2019 CTC


## Task Description

Clinical trials refer to scientific research conducted on human volunteers, also known as subjects, to determine whether they meet specific criteria set by the principal investigator of the trial. These criteria, known as inclusion and exclusion criteria, are generally in the form of unstructured free text. Participant recruitment for clinical trials typically involves manual comparison of medical records and trial screening criteria, a time-consuming and inefficient process. Consequently, clinical trials face numerous challenges, such as difficulty in recruiting participants, lengthy recruitment periods, patient dropouts, and more. Automatically parsing clinical trial screening criteria using natural language processing and machine learning methods to build a system that automates patient screening is a promising research area that holds significant practical application and clinical value.

The main objective of this evaluation task is to classify clinical trial screening criteria. All data for this task are sourced from real clinical trials and have undergone preliminary processing and manual annotation.


## Task Description

In this evaluation, we provide 45 pre-defined categories of screening criteria and a series of Chinese sentences describing clinical trial screening criteria. Participants are required to assign each screening criterion to its specific category. An example is provided below.


| ID | 输入(筛选标准) | 输出(类别)|
|---|---|---|
| S1 | 年龄>80岁 | Age|
| S2 | 近期颅内或椎管内手术史 | Therapy or Surgery |
| S3 | 血糖<2.7mmol/L | Laboratory Examinations |



## Evaluation Metrics

The evaluation metrics for this task include Macro Precision, Macro Recall, and Average F1 score. The final ranking will be based on the Average F1 score.




