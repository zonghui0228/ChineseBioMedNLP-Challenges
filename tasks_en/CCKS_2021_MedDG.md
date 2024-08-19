# CCKS 2021 MedDG


## Task Description

Currently, in China, there are only 2.44 practicing physicians per 1,000 people. Issues such as uneven distribution of medical resources, the hard work of doctors, and long wait times for patient consultations persist. Intelligent medical dialogue systems for smart diagnosis can communicate with patients in real-time, collect patient information, thereby improving clinical diagnostic efficiency, reducing the burden on doctors, and enhancing patient follow-up rates, with broad application prospects. This evaluation task involves entity-based Chinese medical dialogue generation, focusing on dialogue system construction, natural language generation, domain knowledge integration, among other aspects.

The specific definition of the task is as follows: Given the previous K dialogue history H={X_1,X_2,X_3,...,X_K} between doctors and patients, where X_K is the patient's current dialogue statement, and assuming that the doctor's next reply X_(K+1) contains a list of annotated entities E={e_1,e_2,e_3,...,e_K}, the model is required to predict the next reply X_(K+1) based on the dialogue history H. Furthermore, the generated reply should contain as many accurate medical entities (entities in E) as possible. This task is based on a medical dialogue dataset MedDG [1] with annotated entities, involving 12 gastroenterology-related diseases, comprising over 17,000 dialogues and 380,000 sentences. Each dialogue in MedDG is annotated with 160 types of entities related to diseases, symptoms, severity, examinations, and medications.

The challenges of the task include: (1) Medical dialogue system models need to accurately understand the dialogue history and generate relevant responses. (2) In the training set, five classes of entity annotations are provided, and participants need to consider how to utilize this information to assist model training. During the validation and testing phases, the model can only infer potential entities that may be included in the response based on the dialogue history. (3) The medical dialogue data provided for the task is limited, and participants can consider using open-source medical domain-related corpora for model pre-training and transfer learning, such as the MedDialog dataset [3], which offers 34 million unlabeled Chinese dialogues.

- [1] Liu et al. MedDG: A Large-scale Medical Consultation Dataset for Building Medical Dialogue System. ArXiv, 2020.
- [2] Lin et al. Graph-Evolving Meta-Learning for Low-Resource Medical Dialogue Generation. In AAAI, 2021.
- [3] Zeng et al. MedDialog: Large-scale Medical Dialogue Datasets. In EMNLP, 2020.


## Data Description

This task is based on a medical dialogue dataset called MedDG, which includes 12 gastroenterology-related diseases. The training set, train.pk, consists of 14,863 complete dialogues, all annotated with entities from five major categories: diseases, symptoms, attributes, examinations, and medications, totaling 160 related entities. The validation and test sets have examples where entity annotations have been removed, requiring models to generate responses based on the dialogue history. Each correct response in the validation and test examples contains at least one entity. The specific entity types are described as follows:

- Diseases: 12 items, including gastritis, enteritis, constipation, and others.
- Symptoms: 62 items, including diarrhea, abdominal pain, bloating, and others.
- Attributes: 4 items, including duration, inducement, nature, location.
- Examinations: 20 items, including gastroscopy, colonoscopy, stool routine, and others.
- Medications: 62 items, including omeprazole, metronidazole, mosapride, and others.

The entity_list.txt file in the dataset displays the complete list of entities available for reference.

### Training Set Dialogue Examples (with Entity Annotations):

```json
[{'id': 'Patient', 'Sentence': '胃部不适，第一天有痛感，后面就是胀，不拉肚子。就是胀气。请问是什么原因。（男，39岁）', 'Symptom': ['腹泻', '腹胀', '胃肠不适'], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Doctor', 'Sentence': '您好，您的症状有多久了呢？', 'Symptom': [], 'Medicine': [], 'Test': [], 'Attribute': ['时长'], 'Disease': []},
{'id': 'Doctor', 'Sentence': '平时，有没有反酸嗳气，大便情况怎么样？', 'Symptom': ['打嗝', '反流'], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Patient', 'Sentence': '您好，四天了。反酸到不明显。大便正常的。', 'Symptom': ['反流'], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Doctor', 'Sentence': '四天前，有没有吃过凉的东西、辣的东西？有没有腹部受凉？', 'Symptom': [], 'Medicine': [], 'Test': [], 'Attribute': ['诱因'], 'Disease': []},
{'id': 'Patient', 'Sentence': '嗯，那天晚上12点吃了几块凉的饼。', 'Symptom': [], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Patient', 'Sentence': '半夜就开始痛了。', 'Symptom': [], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Doctor', 'Sentence': '您这个情况考虑是饮食所引起的胃肠功能紊乱，目前有消化不良的表现。用过什么药物没有。', 'Symptom': ['消化不良', '胃肠功能紊乱'], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Patient', 'Sentence': '家里找了一些，胃苏冲剂，还有什么xx盐酸什么，但效果不明显。也没有持续吃。', 'Symptom': [], 'Medicine': ['胃苏'], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Doctor', 'Sentence': '建议这几天饮食上清淡一点，不要吃凉的东西，冷的东西。', 'Symptom': [], 'Medicine': [], 'Test': [], 'Attribute': [], 'Disease': []},
{'id': 'Doctor', 'Sentence': '可以口服莫沙比利+金双歧。', 'Symptom': [], 'Medicine': ['莫沙比利', '金双歧'], 'Test': [], 'Attribute': [], 'Disease': []}]
```

### Field Descriptions:

- 'id': The current speaker's identity, 'Patient' represents the patient, 'Doctor' represents the doctor.
- 'Sentence': The specific content of the current sentence.
- 'Symptom': Symptoms entity contained in the current sentence.
- 'Medicine': Medication entity contained in the current sentence.
- 'Test': Examination entity contained in the current sentence.
- 'Attribute': Attribute entity contained in the current sentence.
- 'Disease': Disease entity contained in the current sentence.

### Validation and Test Set Examples (without annotations):

#### Example Input:

```json
[{'history': ['你好，肚脐周围隐隐作痛，不知道怎么回事（女，29岁）',
'你好，这种情况多长时间了？',
'两三天了。',
'隐隐作痛，疼一会就不疼了。',
'还有其他症状吗？恶心想吐吗。',
'没有。',
'是隐隐约约的疼吗。',
'食欲也好的，稍微有点腹胀。']}]
```

#### Example Output:

```json
['可能是胃肠功能紊乱。']
```


## Evaluation Metrics
This task employs three metrics, namely BLEU-1, BLEU-4, and Entity-F1, to assess the quality of medical dialogue generation. The final score of the model is the arithmetic mean of these three metrics.

BLEU-1 and BLEU-4 are used to measure the similarity between the model-generated sentences and the responses provided by the doctors. This evaluation primarily considers character-level unigrams and 4-grams similarity. The specific calculation process can be referenced in the paper [4].

Entity-F1 is utilized to evaluate the accuracy of entities mentioned in the model-generated sentences. The calculation formula is as follows:

precision = Number of annotated entities in the generated sentence / Total number of entities mentioned in the generated sentence
recall = Number of annotated entities in the generated sentence / Total number of annotated entities in the doctor's response

Entity-F1 = (2 * precision * recall) / (precision + recall)

Note: In the evaluation script, the organizers use a string matching method to detect entities appearing in the generated sentences. The string covers all possible entity expressions from the training set. The evaluation script is not disclosed. If participants need to calculate Entity-F1 on their own, they can refer to the entity list entity_list.txt and synonyms mentioned in the training set dialogues.

- [4] Chen et al. A Systematic Comparison of Smoothing Techniques for Sentence-Level BLEU


