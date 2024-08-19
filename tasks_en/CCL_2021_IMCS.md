# CCL 2021 IMCS

## Task Introduction

With the rapid development of "Internet + Healthcare," online consultation platforms are gradually emerging. Online consultation refers to doctors communicating with patients through dialogue to exchange information about the patient's condition, diagnose diseases, and provide relevant medical advice. Under the influence of policies and epidemics, the demand for online consultations is growing rapidly. However, medical resources are scarce, which has prompted the development of automated medical consultation to assist in the diagnosis process through human-machine dialogue.

This intelligent dialogue therapy evaluation sets up three tracks. In the first track, over 2000 sets of medical dialogues are released, covering four pediatric diseases. In the second track, two additional diseases are added, totaling over 800 sets of dialogues. Please refer to the data samples for the specific formats of each track.


## Track One: Medical Dialogue Understanding

### Track Introduction

With the rapid development of "Internet + Medical", online consultation platforms are gradually emerging. Online consultation refers to doctors communicating with patients through dialogue, diagnosing diseases, and providing relevant medical advice. Under the influence of policies and epidemics, the demand for online consultations is growing rapidly. However, doctor resources are scarce, which has prompted the development of automated medical consultations. Automated medical consultations can assist in the diagnosis process through human-machine dialogue, with the understanding of doctor-patient dialogue being an important module. Doctor-patient dialogue understanding mainly involves two tasks, namely named entity recognition and symptom identification.

- Task One: Named Entity Recognition. This task involves identifying important entities from the doctor-patient dialogue text. There are five categories of medical-related entities, annotated using the character-level "BIO" tagging system.

- Task Two: Symptom Identification. This task involves identifying the symptoms that patients have in the doctor-patient dialogue text (a total of 329 normalized symptoms). Each symptom can be classified as having, not having, or uncertain. The task requires participating teams to automatically identify which symptoms the patient has based on the dialogue history.


### Evaluation Method

- Task One: Utilize F1 score as the evaluation metric.

- Task Two: Employ F1 score as the evaluation metric.

- Total Score: The average of the scores obtained in Task One and Task Two.

### Data Example

- Task One: Named Entity Recognition

| Input (对话) | Output (BIO标签)  |
|---|---|
| 医生：有没有发热     | O O O O O O O B-Symptom I-Symptom                    |
| 患者：没有            | O O O O O                                            |
|...|...|
| 医生：应用什么药物   | O O O O O O O O O                                   |
| 患者：给喝过小儿咳喘灵，阿莫西林颗粒 | O O O O O O B-Drug I-Drug I-Drug I-Drug O B-Drug I-Drug I-Drug I-Drug I-Drug I-Drug |
|...|...|

- Task Two: Symptom Identification

|Input（对话） | Output |
|---|---|
|...患者：没有发热，但是咳嗽...患者：嗓子里有呼噜声 | 发热：0 咳嗽：1 痰鸣音：1 |


## Track Two: Medical Report Auto-generation

### Track Introduction

After automated consultations between doctors and patients, it is necessary to write a medical report on the consultation process, describing the overall situation of the patient. To alleviate the pressure on doctors in writing medical reports, we propose automatic generation of medical reports based on the doctor-patient consultation process.

- Task One: Medical Report Generation. This task aims to demonstrate the ability to understand and summarize doctor-patient dialogues in the form of a medical report. Participating teams are required to generate medical reports in a specified format based on patient narratives and doctor-patient dialogues. The report should include six sections: Chief Complaint, Present Illness History, Laboratory Findings, Past Medical History, Diagnosis, and Recommendations.

### Evaluation Method

- Task One: Includes automated evaluation and human evaluation.

  - Automated Evaluation: Calculate the ROUGE score for generating medical reports based on two reference medical reports corresponding to each sample in the dataset.

  - Human Evaluation: After the competition submission channel closes, the top-ranking teams from the automated evaluation phase enter the human evaluation phase. Human evaluators will assess the accuracy, informativeness, fluency, and other dimensions of the generated medical reports.

- Total Score: The average score of Task One (where the second phase score is the average of automated evaluation and human evaluation scores).


### Data Example

|Input（自述+对话）|	Output（医疗报告）|
|---|---|
|自述】宝宝九个月了，嗓子有痰咳不出，很少咳嗽，怎么办【对话】...医生：有没有发热; 患者：没有...医生：应用什么药物;患者：给喝过小儿咳喘灵，阿莫西林颗粒... | (1) 主诉：有痰鸣音两天。(2) 现病史：患儿两天前咳嗽服药好转后，出现痰鸣音，口服小儿咳喘灵，阿莫西林颗粒治疗，症状改善不明显。(3) 辅助检查：听诊。(4) 既往史：暂无。(5) 诊断：小儿支气管炎。(6) 建议：完善胸片，对症治疗 |


## Track Three: Intelligent Medical Diagnosis

### Track Introduction

In a typical offline consultation process, a patient usually starts by introducing their current information and asking questions. After learning about the patient's basic condition, the doctor typically needs to ask the patient several symptom and examination-related questions in succession. Subsequently, the doctor can inform the patient about possible types of diseases they may have and provide medication or examination recommendations. Therefore, the process of consultation is a purposeful sequential interaction. Intelligent medical diagnosis is a key research direction in task-oriented dialogue systems, and this intelligent medical diagnosis competition involves one task.

- Task One: Dialogue System for Disease Recognition. This task requires participating systems to interact with a patient simulator based on the given explicit information (symptoms mentioned in the patient's narrative) to acquire more symptoms from the patient. Based on the interaction content, the system needs to determine the disease.

### Evaluation Method
The evaluation is based on the accuracy of disease identification and the recall rate of symptom identification within a specified number of rounds.

- Task One Evaluation: 0.8 * Accuracy of Disease Identification + 0.2 * Recall Rate of Symptom Identification


### Data Example


| 符号           | 含义                                       |
|----------------|--------------------------------------------|
| id             | 样本id                                    |
| Diagnosis      | 患者疾病类别                              |
| explicit_info  | 病人主诉中明确提及的实体信息，包括症状、检查 |
| implicit_info  | 病人整组对话中提及的症状和检查信息，以及它们类别标签 |






