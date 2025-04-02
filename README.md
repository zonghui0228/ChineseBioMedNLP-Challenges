# ChineseBioNLP-Challenges

This GitHub repository provides a comprehensive review of recent advances in community challenge evaluation competitions for biomedical text mining in China. The repository focuses on the growing field of biomedical natural language processing, which has become increasingly important due to the vast accumulation of textual data from sources such as scientific literature, electronic health records, clinical trial reports, and social media. The repository collects information on various BioNLP tasks, including named entity recognition, entity normalization, attribute extraction, relation extraction, event extraction, text classification, text similarity, knowledge graph construction, question answering, text generation, and large language model evaluation.
`中国生物医学自然语言处理社区挑战学术评估竞赛。这些数据来源包括但不限于科学文献、电子健康记录、临床试验报告和社交媒体等。自然语言处理任务包括但不限于命名实体识别、术语标准化、属性提取、关系提取、事件提取、文本分类、文本相似性、知识图谱构建、问答、文本生成和大语言模型评估。`

## How to cite

Hui Zong, Rongrong Wu, Jiaxue Cha, Weizhe Feng, Erman Wu, Jiakun Li, Aibin Shao, Liang Tao, Zuofeng Li, Buzhou Tang, Bairong Shen. **Advancing Chinese biomedical text mining with community challenges**. Journal of biomedical informatics, 2024;157:104716. pmid: [39197732](https://pubmed.ncbi.nlm.nih.gov/39197732/). doi:[10.1016/j.jbi.2024.104716](https://doi.org/10.1016/j.jbi.2024.104716)


## Introduction

Table summary of community challenges and related evaluation tasks.

| Community challenge | Year | Evaluation task | Brief task description |
|---|---|---|---|
| CCKS | 2023 | PromptCBLUE | CCKS-PromptCBLUE medical large model evaluation`PromptCBLUE医疗大模型评测` |
| CCKS | 2021 | CNER-EE | Entity and event extraction of Chinese electronic medical records`面向中文电子病历的医疗实体及事件抽取` |
| CCKS | 2021 | Phe-Drug-Mol | Link Prediction of Phenotype-Drug-Molecular Multilevel Knowledge Graph`表型-药物-分子多层次知识图谱的链接预测` |
| CCKS | 2021 | MedDG | Chinese Medical Dialogue Generation Incorporating Implicit Entities`蕴含实体的中文医疗对话生成` |
| CCKS | 2021 | CMRC | Reading Comprehension for Chinese Medical Popular Science Knowledge`面向中文医疗科普知识的内容理解` |
| CCKS | 2020 | Covid19 | Construction and Question-Answering of COVID-19 Knowledge Graph`新冠知识图谱构建与问答` |
| CCKS | 2020 | CNER-EE | Entity and event extraction of Chinese electronic medical records`面向中文电子病历的医疗实体及事件抽取` |
| CCKS | 2019 | CNER-AE | Named entity recognition and attribute extraction for electronic health records`面向中文电子病历的医疗实体识别及属性提取` |
| CCKS | 2018 | CNER | Named entity recognition for electronic health records`面向中文电子病历的命名实体识别` |
| CCKS | 2017 | CNER | Named entity recognition for electronic health records`电子病历命名实体识别` |
| CHIP | 2024 | SDTTCM | Syndrome Differentiation Thought in Traditional Chinese Medicine`中医辨证思维评测任务` |
| CHIP | 2024 | LymphomaCoding | Lymphoma Information Extraction and Automatic Coding`淋巴瘤信息抽取及肿瘤编码自动生成任务` |
| CHIP | 2024 | TCDC | Typical Case Diagnosis Consistency`典型病历诊断一致性任务` |
| CHIP | 2023 | PromptCBLUE | CHIP-PromptCBLUE medical large model evaluation`CHIP-PromptCBLUE医疗大模型评测任务` |
| CHIP | 2023 | NER | Chinese medical text few-shot named entity recognition evaluation`中文医学文本小样本命名实体识别评测任务` |
| CHIP | 2023 | MedOCR | Drug paper document recognition and entity relation extraction`药品纸质文档识别与实体关系抽取任务` |
| CHIP | 2023 | YIER-LLM | CHIP-YIER medical large model evaluation task`CHIP-YIER医疗大模型评测任务` |
| CHIP | 2023 | PICOS | Medical literature PICOS identification`医疗文献PICOS识别任务` |
| CHIP | 2023 | DTC | Chinese diabetes question classification evaluation`中文糖尿病问题分类评测任务` |
| CHIP | 2022 | AGAC | Text mining task for gene-disease association semantics`面向“基因-疾病”的关联语义挖掘任务` |
| CHIP | 2022 | CMedCausal | Medical causal entity and relation extraction`医疗因果实体关系抽取任务` |
| CHIP | 2022 | Text2DT | Extracting medical decision trees from medical texts`从医疗文本中抽取诊疗决策树` |
| CHIP | 2022 | MedOCR | Identification of electronic medical paper documents`医疗纸质文档电子档(ePaper)OCR识别` |
| CHIP | 2022 | CDN | Clinical diagnostic coding`临床诊断编码任务` |
| CHIP | 2021 | MDCFNPC | Classifying positive and negative clinical findings in medical dialog`医学对话临床发现阴阳性判别任务` |
| CHIP | 2021 | CDEE | Event extraction of clinical discovery`临床发现事件抽取任务` |
| CHIP | 2021 | CDN | Normalization of Chinese clinical terminology`临床术语标准化任务` |
| CHIP | 2020 | CMeEE | Chinese medical text named entity recognition`中文医学文本命名实体识别` |
| CHIP | 2020 | CMeIE | Chinese medical text relationship extraction`中文医学文本实体关系抽取` |
| CHIP | 2020 | CDN | Clinical terminology normalization`临床术语标准化任务` |
| CHIP | 2020 | Covid19 | Prediction of epidemic trends in COVID-19`新冠肺炎趋势预测` |
| CHIP | 2020 | TCM-QA | Question generation of traditional Chinese medicine literature`中医文献问题生成` |
| CHIP | 2020 | TCM-NER | Entity recognition in traditional Chinese medicine instructions`中药说明书实体识别` |
| CHIP | 2019 | CDN | Clinical terminology normalization`临床术语标准化任务` |
| CHIP | 2019 | STS | Disease question-answering based on transfer learning`平安医疗科技疾病问答迁移学习比赛` |
| CHIP | 2019 | CTC | Text classification of Chinese clinical trials eligibility criteria`临床试验筛选标准短文本分类` |
| CHIP | 2018 | CNER-AE | Entity and attribute extraction of Chinese electronic medical records`中文电子病历中临床医疗实体及属性抽取` |
| CHIP | 2018 | STS | Patient health consultation question pairs matching`平安医疗科技智能患者健康咨询问句匹配大赛` |
| DCIC | 2021 | CNER | Medical entity recognition based on pathology report text`智能医疗决策，病理“金数据”赋能医学诊断` |
| CCL | 2021 | IMCS | Intelligent medical dialogue diagnosis and evaluation`智能医疗对话诊疗评测` |
| CSMI | 2020 | PHQC | Classification of public health questions`公众健康问句分类` |
| CCIR | 2019 | EMR-Query | Data query-based question answering using electronic health records`基于电子病历的数据查询类问答` |


## Evaluation tasks

Note: the original links of evaluation tasks are in Chinese. To enhance information sharing and reach a broader audience, we have provided English translations at the link_en. Furthermore, where applicable, we have included links to GitHub, publication, and leaderboard associated with these tasks.

### CCKS

- ###### 2023
  - PromptCBLUE: CCKS-PromptCBLUE medical large model evaluation`PromptCBLUE医疗大模型评测`
    > The dataset is sourced from the CBLUE benchmark, encompassing 16 scenarios of medical natural language processing tasks, and includes 94 instruction fine-tuning templates.
    > 
    > Dataset size: training set: 68500, validation set: 10270, test set: 20540
    > 
    > [link](https://sigkg.cn/ccks2023/evaluation) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2023_PromptCBLUE.md) | [paper](https://arxiv.org/abs/2310.14151) | [github](https://github.com/michael-wzhu/PromptCBLUE/blob/main/README_EN.md) | [leaderboard1](https://tianchi.aliyun.com/competition/entrance/532084/rankingList) | [leaderboard2](https://tianchi.aliyun.com/competition/entrance/532085/rankingList)

- ###### 2021

  - CNER-EE: Entity and event extraction of Chinese electronic medical records`面向中文电子病历的医疗实体及事件抽取`
    > The medical named entity recognition dataset consists of manually annotated plain text documents from EHRs, identifying medically relevant entities. It includes 6 predefined categories: diseases and diagnoses, examinations, tests, surgeries, medications, and anatomical locations. The medical event extraction dataset includes manually annotated plain text documents from EHRs, focusing on attribute entities related to primary entities of tumor events. It encompasses 3 categories: primary site, lesion size, and metastatic site.
    > 
    > Dataset size: 2800 and 3000
    > 
    > [link](https://sigkg.cn/ccks2021/?page_id=27) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2021_CNER-EE.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-19-0713-5_15) | [leaderboard](https://www.biendata.xyz/competition/ccks_2021_clinic/)

  - Phe-Drug-Mol: Link Prediction of Phenotype-Drug-Molecular Multilevel Knowledge Graph`表型-药物-分子多层次知识图谱的链接预测`
    > A knowledge graph constructed from structured data sourced from reputable websites encompasses 7 types of relationships: associated_with, disease_mapped_to_gene, treats, targets, interacts_with, annotates, and pathway_has_gene_element. 
    > 
    > Dataset size: 80,000 entities, 1,200,000 triples.
    > 
    > [link](https://sigkg.cn/ccks2021/?page_id=27) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2021_Phe-Drug-Mol.md) | [paper](https://link.springer.com/book/10.1007/978-981-19-0713-5) | [leaderboard](https://www.biendata.xyz/competition/ccks_2021_kg_link_prediction/leaderboard/)

  - MedDG: Chinese Medical Dialogue Generation Incorporating Implicit Entities`蕴含实体的中文医疗对话生成`
    > The MedDG dataset, annotated with entities, encompasses 12 types of gastroenterology-related diseases. Each dialogue is annotated with 160 relevant entities across 5 categories: diseases, symptoms, attributes, examinations, and medications. Dataset size: 20,611.
    > 
    > Dataset size: training set: 17864, test set: 4347
    > 
    > [link](https://sigkg.cn/ccks2021/?page_id=27) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2021_MedDG.md) | [paper](https://link.springer.com/book/10.1007/978-981-19-0713-5) | [leaderboard](https://www.biendata.xyz/competition/ccks_2021_mdg/leaderboard/)

  - CMRC: Reading Comprehension for Chinese Medical Popular Science Knowledge`面向中文医疗科普知识的内容理解`
    > The dataset for reading comprehension of medical popular science knowledge includes the main content and a list of question-answer pairs, including question description, question ID, answer list. The dataset of recognizing irrelevant answers in medical popular science knowledge, the format of this dataset is one entry per line, with five columns, including Label, Docid, Question, Description, and Answer.
    > 
    > Dataset size: 36000 and 55000
    > 
    > [link](https://sigkg.cn/ccks2021/?page_id=27) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2021_CMRC.md) | [paper](https://link.springer.com/book/10.1007/978-981-19-0713-5) | [leaderboard](https://www.biendata.xyz/competition/ccks_2021_tencentmedical_1/leaderboard/)

- ###### 2020

  - Covid19: Construction and Question-Answering of COVID-19 Knowledge Graph`新冠知识图谱构建与问答`
    > The COVID-19 knowledge graph encompasses seven entity types: virus, bacteria, disease, drug, medical specialty, examination subject, and symptom. The COVID-19 concept graph additionally includes type relationships between entities and concepts, as well as hierarchical relationships among concepts. The antiviral drug graph includes entities, entity attributes, and relationships between entities. The integrated dataset from the open-domain knowledge base PKUBASE and the OpenKG COVID-19 special topic includes information on entity category triples, hierarchical relationships between types, and predicates. 
    > 
    > Dataset size: This knowledge graph contains 66,499,920 triples, 25,574,536 entities, and 408,690 relations. A training set of 4,000 items, a validation set of 1,529 items, and a test set of 1,599 items
    > 
    > [link](https://sigkg.cn/ccks2020/?page_id=516) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2020_Covid19.md) | [paper](https://bj.bcebos.com/v1/conference/ccks2020/eval_paper/ccks2020_eval_paper_1_1_2.pdf) | [leaderboard1](http://www.biendata.xyz:8002/competition/ccks_2020_7_1/leaderboard/) | [leaderboard2](http://www.biendata.xyz:8002/competition/ccks_2020_7_2/leaderboard/) | [leaderboard3](http://www.biendata.xyz:8002/competition/ccks_2020_7_3/leaderboard/) | [leaderboard4](http://www.biendata.xyz:8002/competition/ccks_2020_7_4/leaderboard/)

  - CNER-EE: Entity and event extraction of Chinese electronic medical records`面向中文电子病历的医疗实体及事件抽取`
    > For medical named entity recognition dataset, it consists of manually annotated entities in EHRs, including diseases and diagnoses, examinations, tests, surgeries, medications, and anatomical locations. For medical event extraction dataset, it comprises manually annotated attribute entities associated with primary entities of oncology events in EHRs. It includes three categories: primary site, lesion size, and metastatic site.
    > 
    > Dataset size: 1500 and 1400
    > 
    > [link](https://sigkg.cn/ccks2020/?page_id=516) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2020_CNER-EE.md) | [paper](https://direct.mit.edu/dint/article/3/3/376/98586/Overview-of-CCKS-2020-Task-3-Named-Entity) | [leaderboard1](http://www.biendata.xyz:8002/competition/ccks_2020_2_1/leaderboard/) | [leaderboard2](http://www.biendata.xyz:8002/competition/ccks_2020_2_2/leaderboard/)

- ###### 2019

  - CNER-AE: Named entity recognition and attribute extraction for electronic health records`面向中文电子病历的医疗实体识别及属性提取`
    > Medical Named Entity Recognition Dataset: The dataset comprises manually annotated documents from EHRs, capturing clinically relevant entities. These entities are categorized into 5 pre-defined categories: Symptoms and Signs, Examinations and Tests, Diseases and Diagnoses, Treatments, and Body Parts. Dataset size: 12,020. Attribute Extraction Dataset: This dataset consists of manually annotated documents from EHRs, focusing on attribute entities related to tumor events. These entities are categorized into 3 types: Lesion Size, Primary Site, and Metastatic Site. Dataset size: 2,000.
    > 
    > Dataset size: 1379
    > 
    > [link](https://www.sigkg.cn/ccks2019/?page_id=62) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2019_CNER-AE.md) | [paper](https://arxiv.org/abs/2003.03875) | [leaderboard](https://www.biendata.xyz/competition/ccks_2019_1/leaderboard/)

- ###### 2018

  - CNER: Named entity recognition for electronic health records`面向中文电子病历的命名实体识别`
    > The dataset consists of manually annotated entities from EHRs, including anatomical sites, symptom descriptions, independent symptoms, medications, and surgeries.
    > 
    > Dataset size: 800
    > 
    > [link](https://www.sigkg.cn/ccks2018/?page_id=1) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2018_CNER.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-15-1956-7_14) | [leaderboard](https://www.biendata.xyz/competition/CCKS2018_1/leaderboard/)

- ###### 2017

  - CNER: Named entity recognition for electronic health records`电子病历命名实体识别`
    > The dataset consists of manually annotated entities from EHRs, including anatomical locations, symptom descriptions, independent symptoms, medications, and surgeries.
    > 
    > Dataset size: 400
    > 
    > [link](https://www.sigkg.cn/ccks2017/?page_id=51) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCKS_2017_CNER.md) | [leaderboard](https://www.biendata.xyz/competition/CCKS2017_2/leaderboard/)


### CHIP

- ###### 2024
  - SDTTCM: Syndrome Differentiation Thought in Traditional Chinese Medicine`中医辨证思维评测任务`
    > The dataset comprises 300 medical case records collected and processed by the task organization to establish a dedicated database. These medical cases were sourced from prominent public platforms such as the "Chinese Journal of Traditional Chinese Medicine" and the "Chinese Medicine Clinical Case Database", known for their high-quality and influential medical case data.
    > 
    > Dataset size: training set: 200, validation set: 50, test set: 50
    > 
    > [link](http://cips-chip.org.cn/2024/eval1) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532222/rankingList)

  - LymphomaCoding: Lymphoma Information Extraction and Automatic Coding`淋巴瘤信息抽取及肿瘤编码自动生成任务`
    > The dataset originates from published Chinese medical clinical case reports. Through a screening process, a total of 162 case reports related to lymphoma diseases have been gathered.
    > 
    > Dataset size: training set: 54, validation set: 54, test set: 54
    > 
    > [link](http://cips-chip.org.cn/2024/eval2) ｜ [leaderboard](https://tianchi.aliyun.com/competition/entrance/532260/rankingList)

  - PTCDC: Typical Case Diagnosis Consistency`典型病历诊断一致性任务`
    > The dataset integrates diagnostic medical records of various common diseases, aiming to comprehensively and objectively evaluate the diagnostic capabilities of medical AI models by accurately replicating the decision-making process of physicians in diagnosing diseases.
    > 
    > Dataset size: training set: 2590, test set: 647
    > 
    > [link](http://cips-chip.org.cn/2024/eval3) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532278/rankingList)

- ###### 2023
  - PromptCBLUE: CHIP-PromptCBLUE medical large model evaluation`CHIP-PromptCBLUE医疗大模型评测任务`
    > The dataset is sourced from the CBLUE benchmark, encompassing 18 scenarios of medical natural language processing tasks, and includes over 450 instruction fine-tuning templates.
    > 
    > Dataset size: training set: 87100, validation set: 8456, test set: 8456
    > 
    > [link](http://cips-chip.org.cn/2023/eval1) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2023_PromptCBLUE.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_1) | [github](https://github.com/michael-wzhu/PromptCBLUE/blob/main/README_EN.md) | [leaderboard1](https://tianchi.aliyun.com/competition/entrance/532131/rankingList) | [leaderboard2](https://tianchi.aliyun.com/competition/entrance/532132/rankingList)

  - NER: Chinese medical text few-shot named entity recognition evaluation`中文医学文本小样本命名实体识别评测任务`
    > The dataset comprises manually annotated entities relevant to medical clinical contexts within medical texts. It includes 15 labels: item, sociology, disease, etiology, body, age, adjuvant, therapy, electroencephalogram, equipment, drug, procedure, treatment, microorganism, department, epidemiology, symptom, and others.
    > 
    > Dataset size: training set: 400, validation set: 100, test set: 100
    > 
    > [link](http://cips-chip.org.cn/2023/eval2) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2023_NER.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_7) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532142/rankingList)

  - MedOCR: Drug paper document recognition and entity relation extraction`药品纸质文档识别与实体关系抽取任务`
    > The drug leaflets were manually annotated for drugs, diseases, and clinical findings.
    > 
    > Dataset size: training set: 400, validation set: 200, test set: 400
    > 
    > [link](http://cips-chip.org.cn/2023/eval3) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2023_MedOCR.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_9) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532140/rankingList)

  - YIER-LLM: CHIP-YIER medical large model evaluation task`CHIP-YIER医疗大模型评测任务`
    > A series of multiple-choice questions constructed from medical entrance exam questions, clinical practice physician assessments, medical textbooks, medical literature/guidelines, and publicly available medical records. Dataset size: 1500.
    > 
    > Dataset size: training set: 1000, test set: 500
    > 
    > [link](http://cips-chip.org.cn/2023/eval4) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2023_YIER-LLM.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_11) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532150/rankingList)

  - PICOS: Medical literature PICOS identification`医疗文献PICOS识别任务`
    > The dataset consists of titles and abstracts from medical publications, annotated with five categories: Population (P), Intervention (I), Comparison (C), Outcome (O), and Study Types (S)
    > 
    > Dataset size: training set: 2500, validation set: 1000, test set: 1000
    > 
    > [link](http://cips-chip.org.cn/2023/eval5) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2023_PICOS.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_14) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532156/rankingList)

  - DTC: Chinese diabetes question classification evaluation`中文糖尿病问题分类评测任务`
    > The dataset consists of diabetes questions from internet, encompassing six categories: diagnosis, treatment, common knowledge, healthy lifestyle, epidemiology, and others.
    > 
    > Dataset size: training set: 6000, validation set: 1000, test set: 1000
    > 
    > [link](http://cips-chip.org.cn/2023/eval6) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2023_DTC.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_18) | [leaderboard](https://tianchi.aliyun.com/competition/entrance/532153/rankingList)

- ###### 2022

  - AGAC: Text mining task for gene-disease association semantics`面向“基因-疾病”的关联语义挖掘任务`
    > The AGAC corpus comprises 12 categories of molecular entities related to "gene-disease" associations and their triggering term entities: Var, MPA, Interaction, Pathway, CPA, Reg, PosReg, NegReg, Disease, Gene, Protein, and Enzyme. It includes semantic role annotations: ThemeOf and CauseOf; regulatory types: Loss of Function (LOF), Gain of Function (GOF), Regulation (REG), and Composite changes in function (COM).
    > 
    > Dataset size: training set: 250, test set: 2000
    > 
    > [link](http://www.cips-chip.org.cn/2022/eval1) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2022_AGAC.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_1)

  - CMedCausal: Medical causal entity and relation extraction`医疗因果实体关系抽取任务`
    > The annotated dialogue corpus includes three types of relationships: "causal", "conditional", and "hyponymy"
    > 
    > Dataset size: training set: 2000, test set: 2000
    > 
    > [link](http://www.cips-chip.org.cn/2022/eval2) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2022_CMedCausal.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_5) | [leaderboard](https://tianchi.aliyun.com/dataset/129573/hasRank)

  - Text2DT: Extracting medical decision trees from medical texts`从医疗文本中抽取诊疗决策树`
    > The dataset consists of extracted diagnostic and therapeutic decision trees from clinical practice guidelines and medical textbooks. A diagnostic and therapeutic decision tree is defined as a binary tree composed of conditional nodes and decision nodes.
    > 
    > Dataset size: training set: 300, validation set: 100, test set: 100
    > 
    > [link](http://www.cips-chip.org.cn/2022/eval3) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2022_Text2DT.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_9)

  - MedOCR: Identification of electronic medical paper documents`医疗纸质文档电子档(ePaper)OCR识别`
    > The dataset consists of scanned images of paper medical records from the internet, defining 87 attributes to be extracted, which include types such as discharge summaries; outpatient invoices; pharmacy purchase invoices; and hospitalization invoices.
    > 
    > Dataset size: training set: 1000, validation set: 200, test set: 500
    > 
    > [link](http://www.cips-chip.org.cn/2022/eval4) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2022_MedOCR.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_13) | [leaderboard](https://tianchi.aliyun.com/dataset/131815/hasRank)

  - CDN: Clinical diagnostic coding`临床诊断编码任务`
    > The dataset comprises annotated information extracted from EHRs, including diagnostic details (such as admission diagnosis, preoperative diagnosis, postoperative diagnosis, and discharge diagnosis), as well as surgical names, medication names, and medical order names.
    > 
    > Dataset size: training set: 2700, test set: 337
    > 
    > [link](http://www.cips-chip.org.cn/2022/eval5) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2022_CDN.md) | [paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_17)

- ###### 2021

  - MDCFNPC: Classifying positive and negative clinical findings in medical dialog`医学对话临床发现阴阳性判别任务`
    > The data comes from publicly available internet-based telemedicine consultations includes patient chief complaints and physician diagnostic judgments, categorized into four attributes: negative, positive, other, and unspecified.
    > 
    > Dataset size: training set: 6000, validation set: 2000, test set: 2000
    > 
    > [link](http://www.cips-chip.org.cn/2021/eval1) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2021_MDCFNPC.md) | [paper](https://kns.cnki.net/kcms2/article/abstract?v=v-1aSqfKcSWRYpBEduJjkBPC8elIBYi-PAojUFRraNbGGkwG0VVNRMVt6Dk2DRe6lurZzseipA_SP7HbybCKwBVTDCl-MRqDfgbjixdEY4bzPQiLgbs0ZzxF9NDHaTeGyFf3TP1NkImiDoV_-uj9xnfpEqGjpy1yiPfLc64VJR1nlnnUXlhDCTBSSnfjvu4aJloU2HuWyxsdFRdFuQUd2hy2TCmFdKZq&uniplatform=NZKPT&language=CHS)

  - CDEE: Event extraction of clinical discovery`临床发现事件抽取任务`
    > The dataset extracted present medical history or imaging findings reports from EHRs, involving attributes across four dimensions: anatomical sites, main terms, descriptive terms, and occurrence status.
    > 
    > Dataset size: training set: 2070, test set: 532
    > 
    > [link](http://www.cips-chip.org.cn/2021/eval2) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2021_CDEE.md)

  - CDN: Normalization of Chinese clinical terminology`临床术语标准化任务`
    > The dataset comprises diagnostic entities, partial surgical entities, and standardized surgical relationship corpora extracted from Chinese EHRs. Dataset size: NA.
    > 
    > Dataset size: training set: 9699, test set: 801
    > 
    > [link](http://www.cips-chip.org.cn/2021/eval3) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2021_CDN.md)

- ###### 2020

  - CMeEE: Chinese medical text named entity recognition`中文医学文本命名实体识别`
    > The dataset comprises 9 entity types extracted through medical text mining: diseases, clinical manifestations, medications, medical devices, medical procedures, anatomical structures, medical laboratory tests, microorganisms, and departments.
    > 
    > Dataset size: training set: 15000, validation set: 5000, test set: 6618
    > 
    > [link](http://www.cips-chip.org.cn/2020/eval1) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2020_CMeEE.md) | [paper](https://kns.cnki.net/kcms2/article/abstract?v=v-1aSqfKcSWc7711zJbMGhEc-7AwSMDPtIufYkckGBtxbW4i0-MuwwIyq7XwM4tTGhq_wKS3fKurlfuP9nE_Ae6w6V9Xq9rJJhFeP7XxyGZTxOoS4PYC8KAotyOHJL93NOVmTz1qLT4lL-zOu2Ng5JtcSp1rZQO9jBrzC4FaRLKV2X-9nrTolkNaxSWDd-yCY3Pkv-rKuGWGNZKuKqTAdr2i7VCaOxMT&uniplatform=NZKPT&language=CHS)

  - CMeIE: Chinese medical text relationship extraction`中文医学文本实体关系抽取`
    > The pediatric training corpus and the corpus extracted from a hundred common diseases yielded 53 schemas, comprising 10 synonymous relations and 43 other relations.
    > 
    > Dataset size: training set: 17924, validation set: 4482, test set: 5602
    > 
    > [link](http://www.cips-chip.org.cn/2020/eval2) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2020_CMeIE.md) | [paper](https://kns.cnki.net/kcms2/article/abstract?v=v-1aSqfKcSX7Zl7_nV_dvRA0a-o_FPPy6Ka_y056XeSvhqnP-SOhpsBdg3sdauGLs1RLNQbDhwUHhH-V9Jl2YxjwQj-TgSkfR07CaZ4MRn2ZE3UtnXV9K6GVmSBaca6UUvXHJhyt1m6iz6imbN9aPjMXsmg6as-st-rQ8HgeUxR_szK_53rRRhrTh9SzsTRR0FO2vsfmY83D0rvohIiM6YuKCmuZYW9q&uniplatform=NZKPT&language=CHS)

  - CDN: Clinical terminology normalization`临床术语标准化任务`
    > The dataset includes diagnostic entities extracted from Chinese EHRs.
    > 
    > Dataset size: training set: 8000, test set: 10000
    > 
    > [link](http://www.cips-chip.org.cn/2020/eval3) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2020_CDN.md)

  - Covid19: Prediction of epidemic trends in COVID-19`新冠肺炎趋势预测`
    > The dataset comprises regional time-series data of confirmed COVID-19 cases, including daily counts of newly diagnosed cases.
    > 
    > Dataset size: nan
    > 
    > [link](http://www.cips-chip.org.cn/2020/eval4) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2020_Covid19.md)

  - TCM-QA: Question generation of traditional Chinese medicine literature`中医文献问题生成`
    > Texts from the field of Traditional Chinese Medicine (TCM), including four TCM books and selected texts from TCM forums, with manually constructed question-answer pairs.
    > 
    > Dataset size: training set: 3500, validation set: 750, test set: 750
    > 
    > [link](http://www.cips-chip.org.cn/2020/eval5) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2020_TCM-QA.md)

  - TCM-NER: Entity recognition in traditional Chinese medicine instructions`中药说明书实体识别`
    > The dataset comprises 13 types of entities extracted from traditional Chinese medicine drug instructions: DRUG, DRUG_INGREDIENT, DISEASE, SYMPTOM, SYNDROME, DISEASE_GROUP, FOOD, FOOD_GROUP, PERSON_GROUP, DRUG_GROUP, DRUG_DOSAGE, DRUG_TASTE, and DRUG_EFFICACY.
    > 
    > Dataset size: training set: 1200, validation set: 400, test set: 397
    > 
    > [link](http://www.cips-chip.org.cn/2020/eval6) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2020_TCM-NER.md)

- ###### 2019

  - CDN: Clinical terminology normalization`临床术语标准化任务`
    > The dataset consists of real surgical entities extracted from Chinese electronic medical records that require standardization.
    > 
    > Dataset size: training set: 4000, validation set: 1000, test set: 2000
    > 
    > [link](http://www.cips-chip.org.cn:8000/evaluation) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2019_CDN.md) | [paper](https://kns.cnki.net/kcms2/article/abstract?v=v-1aSqfKcSVPFys3uZLP0plF-fplQOXU34fp8GNP03ETKCvUXYb-yvxQqU2qWIpeJCyNXfI12shK_bdhRCNj9Mn_6onFv7v-ST5m9tPsoW1uOBB1P-1GtconnY8ur8C742uMyZ-oS4XSTrJCSQXpUP7LWze5lP9iw_lXy8kSXUJNHnU5beFEtKr8U4lhalQIOusZR9wDqUgsSIIGGJo1NedRtTz4AA02&uniplatform=NZKPT&language=CHS)

  - STS: Disease question-answering based on transfer learning`平安医疗科技疾病问答迁移学习比赛`
    > The dataset comprises extracted online disease question-answer sentence pairs related to diabetes, hypertension, hepatitis, aids, and breast cancer.
    > 
    > Dataset size: training set: 20000, validation set: 10000, test set: 50000
    > 
    > [link](http://www.cips-chip.org.cn:8000/evaluation) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2019_STS.md) | [paper](https://kns.cnki.net/kcms2/article/abstract?v=v-1aSqfKcSU-eJzsW5uk05lOW0ogvsxjirYKzXeE1wob9umQA_h0IWCkuzI5tfw4_snIxcsIbbxxd9vRJ8BHIUBqjguvfqV9augDpjjQqUM2nFmynlhgJ6YWSa1Z6Fb2ctppzhQealZdYGr3_8cGtSFKoUlzK4qj2M3_9d-EngTTDEI3uoSnmU5rVX5kU9IbIe9LDN8AdtBTjdiE1hVvcV44cbsOFCclDwUT4ikyVXhMrY1KeSjYUQ==&uniplatform=NZKPT&language=CHS) | [leaderboard](https://www.biendata.xyz/competition/chip2019/leaderboard/)

  - CTC: Text classification of Chinese clinical trials eligibility criteria`临床试验筛选标准短文本分类`
    > Descriptive sentences of Chinese clinical trial inclusion/exclusion criteria, and a predefined set of 44 semantic categories for these criteria.
    > 
    > Dataset size: training set: 22962, validation set: 7682, test set: 7697
    > 
    > [link](http://www.cips-chip.org.cn:8000/evaluation) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2019_CTC.md) | [paper](https://pubmed.ncbi.nlm.nih.gov/33858409/)

- ###### 2018

  - CNER-AE: Entity and attribute extraction of Chinese electronic medical records`中文电子病历中临床医疗实体及属性抽取`
    > Imaging examination reports related to lung cancer and breast cancer.
    > 
    > Dataset size: training set: 600, test set: 200
    > 
    > [link](http://icrc.hitsz.edu.cn/chip2018/Task.html) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2018_CNER-AE.md)

  - STS: Patient health consultation question pairs matching`平安医疗科技智能患者健康咨询问句匹配大赛`
    > The dataset comes from real patient health consultation corpus. Given two sentences, it is required to determine whether the intentions are the same or similar.
    > 
    > Dataset size: training set: 20000, test set: 10000
    > 
    > [link](http://icrc.hitsz.edu.cn/chip2018/Task.html) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CHIP_2018_STS.md)


### DCIC

- ###### 2021

  - CNER: Medical entity recognition based on pathology report text`智能医疗决策，病理“金数据”赋能医学诊断`
    > Extracted 10 types of entities from pathological text.
    > 
    > Dataset size: training set: 1000, test set: 1050
    > 
    > [link](https://www.datafountain.cn/competitions/498) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/DCIC_2021_CNER.md) | [leaderboard](https://www.datafountain.cn/competitions/498/ranking?isRedance=1)

### CCL

- ###### 2021

  - IMCS: Intelligent medical dialogue diagnosis and evaluation`智能医疗对话诊疗评测`
    > The dataset consists of dialogue cases from online medical consultation platforms, utilized for entity recognition, simulated dialogues, and disease diagnosis. Each sample in the dataset includes disease category, patient self-description text, symptoms, and entities and labels inferred from entire medical dialogues.
    > 
    >  Dataset size: >2000
    > 
    > [link](http://www.fudan-disc.com/sharedtask/imcs21/index.html) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCL_2021_IMCS.md)

### CSMI

- ###### 2020

  - PHQC: Classification of public health questions`公众健康问句分类`
    > The dataset consists of public health queries categorized into six major themes: diagnosis, treatment, anatomy/physiology, epidemiology, healthy lifestyle, and choosing healthcare providers. Dataset size: 8000.
    > 
    > Dataset size: training set: 5000, test set: 3000
    > 
    > [link](https://www.heywhale.com/home/competition/5f2d0ea1b4ac2e002c164d82/content) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CSMI_2020_PHQC.md) | [paper](https://kns.cnki.net/kcms2/article/abstract?v=5iIAKlsf9WBSHARREy05MZ-PPhK9bEzInxeo5bHu4SeNGafwR3Op2Ed--tzILIXmqQ9wl57xk5efFRWgtS5g7xoFrkEj4jsfkH8RNSqPAdSv1-41GpBnGmXOTgeCaGSQEQqlvyBdbhQuXN_ig_TzgqPWbZ6sViXiFbd_PAt9boYbxvXa_BZevglCeRTpYn7MBKRSkWDnXLxo_aHwSqsY4IEQK9s2cTsgMAnLo6QlZ8kT6QdT3yIxsVuzyB91aRtO&uniplatform=NZKPT&language=CHS) | [leaderboard](https://www.heywhale.com/home/competition/5f2d0ea1b4ac2e002c164d82/leaderboard)

### CCIR

- ###### 2019

  - EMR-Query: Data query-based question answering using electronic health records`基于电子病历的数据查询类问答`
    > The dataset consists of query-based question-answer pairs derived from EHRs. Dataset size: NA.
    > 
    > Dataset size: training set: 1800, validation set: 600, test set: 600
    > 
    > [link](https://www.biendata.xyz/competition/ccir2019/) | [link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/main/tasks_en/CCIR_2019_EMR-Query.md) | [leaderboard](https://www.biendata.xyz/competition/ccir2019/leaderboard/)


