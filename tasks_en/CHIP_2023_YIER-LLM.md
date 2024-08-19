# CHIP 2023 YIER-LLM


##Task Introduction

In the field of modern healthcare, the application of large medical models has become an important tool for improving patient care and diagnosis. However, ensuring the accuracy and reliability of these models in clinical applications is crucial. This evaluation task aims to assess large medical models through logical reasoning, examining their performance in medical terminology, medical knowledge, clinical standards for diagnosis and treatment, and other medical aspects such as medical calculations.

## Task Details

In this task, the model will need to demonstrate understanding and logical reasoning in medical terminology, medical knowledge, clinical standards for diagnosis and treatment, and medical calculations. The main tasks include the following aspects: the model needs to accurately understand and logically deduce terms and knowledge in the medical field; the model must be able to perform calculations and deductions based on medical formulas, accurately assess patient symptoms, and provide appropriate professional clinical diagnostic knowledge.

## Data Description

The evaluation data will be constructed based on real clinical scenarios, including a series of multiple-choice questions derived from medical entrance exam questions, clinical practitioner questions, medical textbooks, medical literature/guidelines, and publicly available medical records. The dataset will encompass various factors such as different diseases, severity of conditions, patient characteristics, etc., to ensure a comprehensive and realistic evaluation. The dataset will be divided into training and testing sets to ensure the model's generalization ability across different data distributions.


### Data Format

```json
{
   "context":str,
   "question":str,
   "selection":[str1,str2,str3,str4],
   "answer_choices":[str2, str4],
   "sample_id":str,
   "source":str
}
```

Note:
- context: Refers to medical text; please ignore questions with no medical text.
- question: Refers to the question stem.
- selection: Refers to the candidate text items corresponding to the question stem.
- answer_choices: The content of the answers, derived from one or more selections.
- sample_id: The question number designated by the evaluation team.
- source: Indicates the source of the question, such as real questions for clinical practitioners, clinical tests, or questions devised by medical experts.

### Data Example

case1:

```json
{
   "context":"（左侧前列腺）穿刺活检：腺癌（GLeason评分4+3=7分，分级分组3组，），癌组织约占穿刺总体积70%。（右侧前列腺）穿刺活检：腺癌（GLeason评分4+4=8分，分级分组4组，），癌组织约占穿刺总体积60%。",
   "question":"从上述文本中结构化出的【肿瘤部位】正确的是（）",
   "selection":[“前列腺”,“卵巢”,“盆腔”,“腹部”,“以上都不对”],
   "answer_choices":[“前列腺”],
   "sample_id":"sample_13451",
   "source":"医学专家自拟题"
}
```


case2:

```json
{
   "context":"",
   "question":"关于补体调控叙述正确的是",
   "selection":[“补体激活过程中生成的中间产物不稳定","只有结合在细胞表面的抗原抗体复合物才能触发经典途径","补体系统活化失控可造成自身损伤"，"产生病理效应","细胞表面结合有多种补体调节因子","补体调节蛋白有十余种”],
   "answer_choices":[“补体激活过程中生成的中间产物不稳定","只有结合在细胞表面的抗原抗体复合物才能触发经典途径","补体系统活化失控可造成自身损伤"，"细胞表面结合有多种补体调节因子”],
   "sample_id":"sample_1",
   "source":"临床考研真题"
}
```


## Training Evaluation Data

### Data Release:

The evaluation data will be released in two phases:

- September 10th:

Training set release, consisting of 1000 data entries.

- September 25th:

Test set release, comprising 500 data entries. The "answer_choices" field will be empty in the test set.

### Evaluation Metric:

Since the dataset contains multiple-choice answers, the evaluation will use the Micro Average F1 score as the evaluation metric.

This involves summing the counts of true positives, false positives, and false negatives for all answers, then calculating the overall precision, recall, and F1 score.

Micro Average Precision = (Total Correct Answers) / (Total Model Recall Answers)

Micro Average Recall = (Total Correct Answers) / (Total Answers in the Test Data)

Micro Average F1 = 2 * (Micro Average Precision * Micro Average Recall) / (Micro Average Precision + Micro Average Recall)

### Result Submission Format:
Insert the model's predicted answers into the JSON for each test data, with the key "predict_answers" and the value being a list of correct answers.







