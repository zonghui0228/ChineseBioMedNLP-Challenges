# CHIP 2020 CMeIE


## Task Overview

Entity and relation extraction, as important subtasks of information extraction, have been extensively researched in recent years by numerous scholars using various technologies in this field. Applying these technologies to the medical domain, extracting unstructured and semi-structured medical texts to construct a medical knowledge graph can serve downstream subtasks. Unstructured medical texts, such as each natural paragraph in medical textbooks, topics under each disease in clinical practice, chief complaints, present illness history, differential diagnoses in electronic medical record data, are all composed of Chinese natural language sentences or sets of sentences. Entity relation extraction is the process of identifying medical entities from unstructured medical texts and determining the factual relationships between entities.

## Task Details

Given a schema constraint set and a sentence, where the schema defines the relationship predicate along with the categories of its subject and object, for example:

("subject_type": "disease", "predicate": "drug treatment", "object_type": "drug") ("subject_type": "disease", "predicate": "laboratory test", "object_type": "test")

The task requires the participating system to automatically analyze the sentence, outputting all SPO triples that satisfy the schema constraints in the sentence, forming Triples=[(S1, P1, O1), (S2, P2, O2)...].

### Input/Output:

**Input:** Schema constraint set and the sentence

**Output:** Triples of knowledge contained in the sentence that meet the given schema constraints



## Data Overview

The dataset used in this competition was jointly constructed by the Natural Language Processing Laboratory of Zhengzhou University, the Key Laboratory of Computational Linguistics at Peking University under the Ministry of Education, Harbin Institute of Technology (Shenzhen), and the Smart Healthcare Project Team at the Peng Cheng Laboratory Artificial Intelligence Research Center. This dataset is based on the schema-based Chinese Medical Information Extraction dataset (CMeIE). It includes pediatric training corpus and training corpus for a hundred common diseases. The pediatric training corpus is sourced from 518 pediatric diseases, while the training corpus for a hundred common diseases is sourced from 109 common diseases. The dataset comprises nearly 75,000 triples, 28,000 disease sentences, and 53 predefined schemas.

Compared to medical textbooks, clinical practice texts exhibit explicit referential relationships. Often, a paragraph may not directly mention the topic disease, so preprocessing is done for clinical practice corpora. Rules are designed to add the topic disease entity before each sentence, separated from the original text by "@" to handle this. When extracting data, if triples originate from multiple sentences, these sentences are concatenated, with the "Combined" field in the "spo_list" recording this information. If there are multiple triples in a sentence, they are recorded in the "spo_list" field, with the "text" field documenting the source text.


```json
{"text": "慢性胰腺炎@### 低剂量放射 自1964年起，有几项病例系列报道称外照射 (5-50Gy)
        可以有效改善慢性胰腺炎患者的疼痛症状。慢性胰腺炎@从概念上讲，外照射可以起到抗炎和止痛作用，并且已经开始被用于非肿瘤性疼痛的治疗。",

        "spo_list": [

        {"Combined": true, "predicate": "放射治疗", "subject": "慢性胰腺炎", "subject_type": "疾病", "object": {"@value": "外照射"},
        "object_type": {"@value": "其他治疗"}},

        {"Combined": true, "predicate": "放射治疗", "subject": "非肿瘤性疼痛", "subject_type": "疾病", "object": {"@value": "外照射"},
        "object_type": {"@value": "其他治疗"}}
        ]
}
```

The table below shows the 53 schemas included in the dataset, comprising 10 synonym sub-relations (merged into one in Table 1) and 43 other sub-relations. The corpus in the dataset is sourced from medical textbooks and medical texts such as clinical practice. The dataset is divided as follows: Training Set (17,924 samples), Test Set 1 (4,482 samples), Test Set 2 (5,602 samples). The training set is used for training and is freely available for download. Test Set 1 is for participants to independently verify on the platform, while Test Set 2 will be released one week before the end of the competition and cannot be independently verified on the platform. Test Set 2 will be used for the final evaluation ranking.



## Evaluation Metrics

Participants' SPO results on the test sets (Test1 and Test2) are compared against the annotated results in the test sets for precise matching. Precision, Recall, and F1 score are used as evaluation metrics for assessing the performance.







