# CHIP 2023 PICOS


## Task Background

With the development of modern medical informatics and databases, medical professionals are increasingly inclined to use evidence-based medicine to guide their learning and work. Evidence-based medicine requires a large amount of query materials and literature information. The PICOS retrieval method enhances the efficiency of evidence-based retrieval. Following the release of the "Medical Dialogue Clinical Finding Positive and Negative Discrimination Task" at the CHIP 2021 conference and the "Medical Causality Extraction Task" at the CHIIP 2022 conference, this year Alibaba's Quark Medical team released the "Medical Paper PICOS Key Information Extraction Task".

## Task Introduction

### Task Description

Introduction to the PICOS principle:

- P (Population): The study population. A specific group of people with a certain disease.

- I (Intervention): Intervention measures. The treatment plan or exposure factors of the intervention group.

- C (Comparison): Comparison measures. The treatment plan or exposure factors of the control group.

- O (Outcome): Outcome. Important clinical outcomes, such as effectiveness and survival rates.

- S (Study design): Study type. What is the study design, whether it is a randomized controlled study or a cohort study, case-control study?

In academic searches, most searches are actually keyword searches, which involve two key roles of keyword information:

- Medical intent of the study (S): Classification of titles.
- Decision information of keywords (PICO): Mention recognition in titles.

Based on this, we have made adjustments to the task, annotating the Title and Content separately.



### Annotation Guidelines

- For Title
  - a) Firstly, annotate the type of the Title: including treatment, diagnosis, etiology, prognosis, clinical statistics, standard guideline recommendations.
  - b) Core elements in the Title need to be annotated: study population (P), intervention (I), assessment items and assessment methods (O).

- For Content
  - a) Initially focus on sentence-level classification: divided into research purpose, research methods, quantitative conclusions, qualitative conclusions.

### Annotation Example

```json
{
   "text":"蒙药瘀紫丸治疗原发性血小板减少性紫癜,疗效显著,副作用少,观察组43例,显效11例,占25.6%;良效21例,占48.8%;进步7例,占16.3%;无效4例,占9.3%;总有效率为90.7%,并且血热偏盛型疗效优于寒热交博型。",
   "ner_list":[
    {
     "mention":“蒙药瘀紫丸治疗原发性血小板减少性紫癜,疗效显著,副作用少。”,
     "label":"O-定性结论”
    },
    {
     "mention":“观察组43例,显效11例,占25.6%;良效21例,占48.8%;进步7例,占16.3%;无效4例,占9.3%;总有效率为90.7%,并且血热偏盛型疗效优于寒热交博型。”,
     "label":"O-定量结论”
    }
   ]
}
```

```json
{
   "text":"蒙医药治疗特发性血小板减少性紫癜临床观察",
   "ner_list":[
    {
     "mention":“蒙医药治疗特发性血小板减少性紫癜临床观察”,
     "label":"S-治疗”
    },
    {
     "mention":“特发性血小板减少性紫癜临”,
     "label":"P-人群/患者类型”
    },
    {
     "mention":“蒙医药治”,
     "label":"I-药物干预”
    }
   ]
  }
```

### Data Description:

- text: Represents textual information, with Abstract and Title interspersed line by line.
- ner_list: List for annotating Mention and Type.
  - a) label indicates the type information for PICOS.
  - b) mention indicates the Mention information corresponding to the type.


## Evaluation Data

For this evaluation, 2500 papers' titles and abstracts are provided as the training set. A and B sets each contain 1000 papers' titles and abstracts as test data, with the constraint that B set training is limited to within 48 hours.

## Evaluation Metric

The evaluation will use Macro-F1 as the assessment metric.


Note: In order for a prediction to be considered correct, it is necessary that (head entity mention, relationship type, tail entity mention) are all predicted correctly. Particularly for conditional relationships, only when (condition mention, conditional relationship, (cause mention, causal relationship, result mention)) are all predicted correctly, it will be considered as a correct prediction.



