# ChineseBioNLP-Challenges

This GitHub repository provides a comprehensive review of recent advances in community challenge evaluation competitions for biomedical text mining in China. The repository focuses on the growing field of biomedical natural language processing, which has become increasingly important due to the vast accumulation of textual data from sources such as scientific literature, electronic health records, clinical trial reports, and social media. The repository collects information on various BioNLP tasks, including named entity recognition, entity normalization, attribute extraction, relation extraction, event extraction, text classification, text similarity, knowledge graph construction, question answering, text generation, and large language model evaluation.


## Introduction

Table summary of community challenges and related evaluation tasks.

| Community challenge | Year | Evaluation task | Brief task description |
|---------------------|------|-----------------|-----------------------|
| CCKS | 2023 | PromptCBLUE | CCKS-PromptCBLUE medical large model evaluation |
| CCKS | 2021 | CNER-EE | Entity and event extraction of Chinese electronic medical records |
| CCKS | 2021 | Phe-Drug-Mol | Link Prediction of Phenotype-Drug-Molecular Multilevel Knowledge Graph |
| CCKS | 2021 | MedDG | Chinese Medical Dialogue Generation Incorporating Implicit Entities |
| CCKS | 2021 | CMRC | Reading Comprehension for Chinese Medical Popular Science Knowledge |
| CCKS | 2020 | Covid19 | Construction and Question-Answering of COVID-19 Knowledge Graph |
| CCKS | 2020 | CNER-EE | Entity and event extraction of Chinese electronic medical records |
| CCKS | 2019 | CNER-AE | Named entity recognition and attribute extraction for electronic health records |
| CCKS | 2018 | CNER | Named entity recognition for electronic health records |
| CCKS | 2017 | CNER | Named entity recognition for electronic health records |
| CHIP | 2023 | PromptCBLUE | CHIP-PromptCBLUE medical large model evaluation |
| CHIP | 2023 | NER | Chinese medical text few-shot named entity recognition evaluation |
| CHIP | 2023 | MedOCR | Drug paper document recognition and entity relation extraction |
| CHIP | 2023 | YIER-LLM | CHIP-YIER medical large model evaluation task |
| CHIP | 2023 | PICOS | Medical literature PICOS identification |
| CHIP | 2023 | DTC | Chinese diabetes question classification evaluation |
| CHIP | 2022 | AGAC | Text mining task for gene-disease association semantics |
| CHIP | 2022 | CMedCausal | Medical causal entity and relation extraction |
| CHIP | 2022 | Text2DT | Extracting medical decision trees from medical texts |
| CHIP | 2022 | MedOCR | Identification of electronic medical paper documents |
| CHIP | 2022 | CDN | Clinical diagnostic coding |
| CHIP | 2021 | MDCFNPC | Classifying positive and negative clinical findings in medical dialog |
| CHIP | 2021 | CDEE | Event extraction of clinical discovery |
| CHIP | 2021 | CDN | Normalization of Chinese clinical terminology |
| CHIP | 2020 | CMeEE | Chinese medical text named entity recognition |
| CHIP | 2020 | CMeIE | Chinese medical text relationship extraction |
| CHIP | 2020 | CDN | Clinical terminology normalization |
| CHIP | 2020 | Covid19 | Prediction of epidemic trends in COVID-19 |
| CHIP | 2020 | TCM-QA | Question generation of traditional Chinese medicine literature |
| CHIP | 2020 | TCM-NER | Entity recognition in traditional Chinese medicine instructions |
| CHIP | 2019 | CDN | Clinical terminology normalization |
| CHIP | 2019 | STS | Disease question-answering based on transfer learning |
| CHIP | 2019 | CTC | Text classification of Chinese clinical trials eligibility criteria |
| CHIP | 2018 | CNER-AE | Entity and attribute extraction of Chinese electronic medical records |
| CHIP | 2018 | STS | Patient health consultation question pairs matching |
| DCIC | 2021 | CNER | Medical entity recognition based on pathology report text |
| CCL | 2021 | IMCS | Intelligent medical dialogue diagnosis and evaluation |
| CSMI | 2020 | PHQC | Classification of public health questions |
| CCIR | 2019 | EMR-Query | Data query-based question answering using electronic health records |


## Evaluation tasks

Note: the original links of evaluation tasks are in Chinese. To enhance information sharing and reach a broader audience, we have provided English translations at the link_en. Furthermore, where applicable, we have included links to GitHub, publication, and leaderboard associated with these tasks.

### CCKS

- ###### 2023
  - PromptCBLUE: CCKS-PromptCBLUE medical large model evaluation
    > The dataset is sourced from the CBLUE benchmark, encompassing 16 scenarios of medical natural language processing tasks, and includes 94 instruction fine-tuning templates.
    > 
    > Dataset size: training set: 68500, validation set: 10270, test set: 20540
    > 
    > **[link](https://sigkg.cn/ccks2023/evaluation)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2023_PromptCBLUE.md)** | **[paper](https://arxiv.org/abs/2310.14151)** | **[github](https://github.com/michael-wzhu/PromptCBLUE/blob/main/README_EN.md)** | **[leaderboard1](https://tianchi.aliyun.com/competition/entrance/532084/rankingList)** | **[leaderboard2](https://tianchi.aliyun.com/competition/entrance/532085/rankingList)**

- ###### 2021

  - CNER-EE: Entity and event extraction of Chinese electronic medical records
    > The medical named entity recognition dataset consists of manually annotated plain text documents from EHRs, identifying medically relevant entities. It includes 6 predefined categories: diseases and diagnoses, examinations, tests, surgeries, medications, and anatomical locations. The medical event extraction dataset includes manually annotated plain text documents from EHRs, focusing on attribute entities related to primary entities of tumor events. It encompasses 3 categories: primary site, lesion size, and metastatic site.
    > 
    > Dataset size: 2800 and 3000
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2021_CNER-EE.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-19-0713-5_15)** | **[leaderboard](https://www.biendata.xyz/competition/ccks_2021_clinic/)**

  - Phe-Drug-Mol: Link Prediction of Phenotype-Drug-Molecular Multilevel Knowledge Graph
    > A knowledge graph constructed from structured data sourced from reputable websites encompasses 7 types of relationships: associated_with, disease_mapped_to_gene, treats, targets, interacts_with, annotates, and pathway_has_gene_element. 
    > 
    > Dataset size: 80,000 entities, 1,200,000 triples.
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2021_Phe-Drug-Mol.md)** | **[leaderboard](https://www.biendata.xyz/competition/ccks_2021_kg_link_prediction/leaderboard/)**

  - MedDG: Chinese Medical Dialogue Generation Incorporating Implicit Entities
    > The MedDG dataset, annotated with entities, encompasses 12 types of gastroenterology-related diseases. Each dialogue is annotated with 160 relevant entities across 5 categories: diseases, symptoms, attributes, examinations, and medications. Dataset size: 20,611.
    > 
    > Dataset size: training set: 17864, test set: 4347
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2021_MedDG.md)** | **[leaderboard](https://www.biendata.xyz/competition/ccks_2021_mdg/leaderboard/)**

  - CMRC: Reading Comprehension for Chinese Medical Popular Science Knowledge
    > The dataset for reading comprehension of medical popular science knowledge includes the main content and a list of question-answer pairs, including question description, question ID, answer list. The dataset of recognizing irrelevant answers in medical popular science knowledge, the format of this dataset is one entry per line, with five columns, including Label, Docid, Question, Description, and Answer.
    > 
    > Dataset size: 36000 and 55000
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2021_CMRC.md)** | **[leaderboard](https://www.biendata.xyz/competition/ccks_2021_tencentmedical_1/leaderboard/)**

- ###### 2020

  - Covid19: Construction and Question-Answering of COVID-19 Knowledge Graph
    > The COVID-19 knowledge graph encompasses seven entity types: virus, bacteria, disease, drug, medical specialty, examination subject, and symptom. The COVID-19 concept graph additionally includes type relationships between entities and concepts, as well as hierarchical relationships among concepts. The antiviral drug graph includes entities, entity attributes, and relationships between entities. The integrated dataset from the open-domain knowledge base PKUBASE and the OpenKG COVID-19 special topic includes information on entity category triples, hierarchical relationships between types, and predicates. 
    > 
    > Dataset size: This knowledge graph contains 66,499,920 triples, 25,574,536 entities, and 408,690 relations. A training set of 4,000 items, a validation set of 1,529 items, and a test set of 1,599 items
    > 
    > **[link](https://sigkg.cn/ccks2020/?page_id=516)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2020_Covid19.md)** | **[paper](https://bj.bcebos.com/v1/conference/ccks2020/eval_paper/ccks2020_eval_paper_1_1_2.pdf)** | **[leaderboard1](#http://www.biendata.xyz:8002/competition/ccks_2020_7_1/leaderboard/)** | **[leaderboard2](http://www.biendata.xyz:8002/competition/ccks_2020_7_2/leaderboard/)** | **[leaderboard3](http://www.biendata.xyz:8002/competition/ccks_2020_7_3/leaderboard/)** | **[leaderboard4](http://www.biendata.xyz:8002/competition/ccks_2020_7_4/leaderboard/)**

  - CNER-EE: Entity and event extraction of Chinese electronic medical records
    > For medical named entity recognition dataset, it consists of manually annotated entities in EHRs, including diseases and diagnoses, examinations, tests, surgeries, medications, and anatomical locations. For medical event extraction dataset, it comprises manually annotated attribute entities associated with primary entities of oncology events in EHRs. It includes three categories: primary site, lesion size, and metastatic site.
    > 
    > Dataset size: 1500 and 1400
    > 
    > **[link](https://sigkg.cn/ccks2020/?page_id=516)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2020_CNER-EE.md)** | **[paper](https://bj.bcebos.com/v1/conference/ccks2020/eval_paper/ccks2020_eval_paper_3_1_1.pdf)** | **[leaderboard1](http://www.biendata.xyz:8002/competition/ccks_2020_2_1/leaderboard/)** | **[leaderboard2](http://www.biendata.xyz:8002/competition/ccks_2020_2_2/leaderboard/)**

- ###### 2019

  - CNER-AE: Named entity recognition and attribute extraction for electronic health records
    > Medical Named Entity Recognition Dataset: The dataset comprises manually annotated documents from EHRs, capturing clinically relevant entities. These entities are categorized into 5 pre-defined categories: Symptoms and Signs, Examinations and Tests, Diseases and Diagnoses, Treatments, and Body Parts. Dataset size: 12,020. Attribute Extraction Dataset: This dataset consists of manually annotated documents from EHRs, focusing on attribute entities related to tumor events. These entities are categorized into 3 types: Lesion Size, Primary Site, and Metastatic Site. Dataset size: 2,000.
    > 
    > Dataset size: 1379
    > 
    > **[link](https://www.sigkg.cn/ccks2019/?page_id=62)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2019_CNER-AE.md)** | **[leaderboard](https://www.biendata.xyz/competition/ccks_2019_1/leaderboard/)**

- ###### 2018

  - CNER: Named entity recognition for electronic health records
    > The dataset consists of manually annotated entities from EHRs, including anatomical sites, symptom descriptions, independent symptoms, medications, and surgeries.
    > 
    > Dataset size: 800
    > 
    > **[link](https://www.sigkg.cn/ccks2018/?page_id=1)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2018_CNER.md)** | **[leaderboard](https://www.biendata.xyz/competition/CCKS2018_1/leaderboard/)**

- ###### 2017

  - CNER: Named entity recognition for electronic health records
    > The dataset consists of manually annotated entities from EHRs, including anatomical locations, symptom descriptions, independent symptoms, medications, and surgeries.
    > 
    > Dataset size: 400
    > 
    > **[link](https://www.sigkg.cn/ccks2017/?page_id=51)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCKS_2017_CNER.md)** | **[leaderboard](https://www.biendata.xyz/competition/CCKS2017_2/leaderboard/)**


### CHIP

- ###### 2023
  - PromptCBLUE: CHIP-PromptCBLUE medical large model evaluation
    > The dataset is sourced from the CBLUE benchmark, encompassing 18 scenarios of medical natural language processing tasks, and includes over 450 instruction fine-tuning templates.
    > 
    > Dataset size: training set: 87100, validation set: 8456, test set: 8456
    > 
    > **[link](http://cips-chip.org.cn/2023/eval1)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2023_PromptCBLUE.md)** **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_1)** | **[leaderboard1](https://tianchi.aliyun.com/competition/entrance/532131/rankingList)** | **[leaderboard2](https://tianchi.aliyun.com/competition/entrance/532132/rankingList)**

  - NER: Chinese medical text few-shot named entity recognition evaluation
    > The dataset comprises manually annotated entities relevant to medical clinical contexts within medical texts. It includes 15 labels: item, sociology, disease, etiology, body, age, adjuvant, therapy, electroencephalogram, equipment, drug, procedure, treatment, microorganism, department, epidemiology, symptom, and others.
    > 
    > Dataset size: training set: 400, validation set: 100, test set: 100
    > 
    > **[link](http://cips-chip.org.cn/2023/eval2)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2023_NER.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_7)** | **[leaderboard](https://tianchi.aliyun.com/competition/entrance/532142/rankingList)**

  - MedOCR: Drug paper document recognition and entity relation extraction
    > The drug leaflets were manually annotated for drugs, diseases, and clinical findings.
    > 
    > Dataset size: training set: 400, validation set: 200, test set: 400
    > 
    > **[link](http://cips-chip.org.cn/2023/eval3)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2023_MedOCR.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_9)** | **[leaderboard](https://tianchi.aliyun.com/competition/entrance/532140/rankingList)**

  - YIER-LLM: CHIP-YIER medical large model evaluation task
    > A series of multiple-choice questions constructed from medical entrance exam questions, clinical practice physician assessments, medical textbooks, medical literature/guidelines, and publicly available medical records. Dataset size: 1500.
    > 
    > Dataset size: training set: 1000, test set: 500
    > 
    > **[link](http://cips-chip.org.cn/2023/eval4)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2023_YIER-LLM.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_11)** | **[leaderboard](https://tianchi.aliyun.com/competition/entrance/532150/rankingList)**

  - PICOS: Medical literature PICOS identification
    > The dataset consists of titles and abstracts from medical publications, annotated with five categories: Population (P), Intervention (I), Comparison (C), Outcome (O), and Study Types (S)
    > 
    > Dataset size: training set: 2500, validation set: 1000, test set: 1000
    > 
    > **[link](http://cips-chip.org.cn/2023/eval5)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2023_PICOS.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_14)** | **[leaderboard](https://tianchi.aliyun.com/competition/entrance/532156/rankingList)**

  - DTC: Chinese diabetes question classification evaluation
    > The dataset consists of diabetes questions from internet, encompassing six categories: diagnosis, treatment, common knowledge, healthy lifestyle, epidemiology, and others.
    > 
    > Dataset size: training set: 6000, validation set: 1000, test set: 1000
    > 
    > **[link](http://cips-chip.org.cn/2023/eval6)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2023_DTC.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_18)** | **[leaderboard](https://tianchi.aliyun.com/competition/entrance/532153/rankingList)**

- ###### 2022

  - AGAC: Text mining task for gene-disease association semantics
    > The AGAC corpus comprises 12 categories of molecular entities related to "gene-disease" associations and their triggering term entities: Var, MPA, Interaction, Pathway, CPA, Reg, PosReg, NegReg, Disease, Gene, Protein, and Enzyme. It includes semantic role annotations: ThemeOf and CauseOf; regulatory types: Loss of Function (LOF), Gain of Function (GOF), Regulation (REG), and Composite changes in function (COM).
    > 
    > Dataset size: training set: 250, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval1)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2022_AGAC.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_1)**

  - CMedCausal: Medical causal entity and relation extraction
    > The annotated dialogue corpus includes three types of relationships: "causal", "conditional", and "hyponymy"
    > 
    > Dataset size: training set: 2000, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval2)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2022_CMedCausal.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_5)** | **[leaderboard](https://tianchi.aliyun.com/dataset/129573/hasRank)**

  - Text2DT: Extracting medical decision trees from medical texts
    > The dataset consists of extracted diagnostic and therapeutic decision trees from clinical practice guidelines and medical textbooks. A diagnostic and therapeutic decision tree is defined as a binary tree composed of conditional nodes and decision nodes.
    > 
    > Dataset size: training set: 300, validation set: 100, test set: 100
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval3)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2022_Text2DT.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_9)**

  - MedOCR: Identification of electronic medical paper documents
    > The dataset consists of scanned images of paper medical records from the internet, defining 87 attributes to be extracted, which include types such as discharge summaries; outpatient invoices; pharmacy purchase invoices; and hospitalization invoices.
    > 
    > Dataset size: training set: 1000, validation set: 200, test set: 500
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval4)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2022_MedOCR.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_13)** | **[leaderboard](https://tianchi.aliyun.com/dataset/131815/hasRank)**

  - CDN: Clinical diagnostic coding
    > The dataset comprises annotated information extracted from EHRs, including diagnostic details (such as admission diagnosis, preoperative diagnosis, postoperative diagnosis, and discharge diagnosis), as well as surgical names, medication names, and medical order names.
    > 
    > Dataset size: training set: 2700, test set: 337
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval5)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2022_CDN.md)** | **[paper](https://link.springer.com/chapter/10.1007/978-981-99-4826-0_17)**

- ###### 2021

  - MDCFNPC: Classifying positive and negative clinical findings in medical dialog
    > The data comes from publicly available internet-based telemedicine consultations includes patient chief complaints and physician diagnostic judgments, categorized into four attributes: negative, positive, other, and unspecified.
    > 
    > Dataset size: training set: 6000, validation set: 2000, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn/2021/eval1)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2021_MDCFNPC.md)**

  - CDEE: Event extraction of clinical discovery
    > The dataset extracted present medical history or imaging findings reports from EHRs, involving attributes across four dimensions: anatomical sites, main terms, descriptive terms, and occurrence status.
    > 
    > Dataset size: training set: 2070, test set: 532
    > 
    > **[link](http://www.cips-chip.org.cn/2021/eval2)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2021_CDEE.md)**

  - CDN: Normalization of Chinese clinical terminology
    > The dataset comprises diagnostic entities, partial surgical entities, and standardized surgical relationship corpora extracted from Chinese EHRs. Dataset size: NA.
    > 
    > Dataset size: training set: 9699, test set: 801
    > 
    > **[link](http://www.cips-chip.org.cn/2021/eval3)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2021_CDN.md)**

- ###### 2020

  - CMeEE: Chinese medical text named entity recognition
    > The dataset comprises 9 entity types extracted through medical text mining: diseases, clinical manifestations, medications, medical devices, medical procedures, anatomical structures, medical laboratory tests, microorganisms, and departments.
    > 
    > Dataset size: training set: 15000, validation set: 5000, test set: 6618
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval1)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2020_CMeEE.md)**

  - CMeIE: Chinese medical text relationship extraction
    > The pediatric training corpus and the corpus extracted from a hundred common diseases yielded 53 schemas, comprising 10 synonymous relations and 43 other relations.
    > 
    > Dataset size: training set: 17924, validation set: 4482, test set: 5602
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval2)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2020_CMeIE.md)**

  - CDN: Clinical terminology normalization
    > The dataset includes diagnostic entities extracted from Chinese EHRs.
    > 
    > Dataset size: training set: 8000, test set: 10000
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval3)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2020_CDN.md)**

  - Covid19: Prediction of epidemic trends in COVID-19
    > The dataset comprises regional time-series data of confirmed COVID-19 cases, including daily counts of newly diagnosed cases.
    > 
    > Dataset size: nan
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval4)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2020_Covid19.md)**

  - TCM-QA: Question generation of traditional Chinese medicine literature
    > Texts from the field of Traditional Chinese Medicine (TCM), including four TCM books and selected texts from TCM forums, with manually constructed question-answer pairs.
    > 
    > Dataset size: training set: 3500, validation set: 750, test set: 750
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval5)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2020_TCM-QA.md)**

  - TCM-NER: Entity recognition in traditional Chinese medicine instructions
    > The dataset comprises 13 types of entities extracted from traditional Chinese medicine drug instructions: DRUG, DRUG_INGREDIENT, DISEASE, SYMPTOM, SYNDROME, DISEASE_GROUP, FOOD, FOOD_GROUP, PERSON_GROUP, DRUG_GROUP, DRUG_DOSAGE, DRUG_TASTE, and DRUG_EFFICACY.
    > 
    > Dataset size: training set: 1200, validation set: 400, test set: 397
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval6)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2020_TCM-NER.md)**

- ###### 2019

  - CDN: Clinical terminology normalization
    > The dataset consists of real surgical entities extracted from Chinese electronic medical records that require standardization.
    > 
    > Dataset size: training set: 4000, validation set: 1000, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn:8000/evaluation)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2019_CDN.md)**

  - STS: Disease question-answering based on transfer learning
    > The dataset comprises extracted online disease question-answer sentence pairs related to diabetes, hypertension, hepatitis, aids, and breast cancer.
    > 
    > Dataset size: training set: 20000, validation set: 10000, test set: 50000
    > 
    > **[link](http://www.cips-chip.org.cn:8000/evaluation)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2019_STS.md)** | **[leaderboard](https://www.biendata.xyz/competition/chip2019/leaderboard/)**

  - CTC: Text classification of Chinese clinical trials eligibility criteria
    > Descriptive sentences of Chinese clinical trial inclusion/exclusion criteria, and a predefined set of 44 semantic categories for these criteria.
    > 
    > Dataset size: training set: 22962, validation set: 7682, test set: 7697
    > 
    > **[link](http://www.cips-chip.org.cn:8000/evaluation)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2019_CTC.md)** | **[paper](https://pubmed.ncbi.nlm.nih.gov/33858409/)**

- ###### 2018

  - CNER-AE: Entity and attribute extraction of Chinese electronic medical records
    > Imaging examination reports related to lung cancer and breast cancer.
    > 
    > Dataset size: training set: 600, test set: 200
    > 
    > **[link](http://icrc.hitsz.edu.cn/chip2018/Task.html)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2018_CNER-AE.md)**

  - STS: Patient health consultation question pairs matching
    > The dataset comes from real patient health consultation corpus. Given two sentences, it is required to determine whether the intentions are the same or similar.
    > 
    > Dataset size: training set: 20000, test set: 10000
    > 
    > **[link](http://icrc.hitsz.edu.cn/chip2018/Task.html)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CHIP_2018_STS.md)**


### DCIC

- ###### 2021

  - CNER: Medical entity recognition based on pathology report text
    > Extracted 10 types of entities from pathological text.
    > 
    > Dataset size: training set: 1000, test set: 1050
    > 
    > **[link](https://www.datafountain.cn/competitions/498)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/DCIC_2021_CNER.md)** | **[leaderboard](https://www.datafountain.cn/competitions/498/ranking?isRedance=1)**

### CCL

- ###### 2021

  - IMCS: Intelligent medical dialogue diagnosis and evaluation
    > The dataset consists of dialogue cases from online medical consultation platforms, utilized for entity recognition, simulated dialogues, and disease diagnosis. Each sample in the dataset includes disease category, patient self-description text, symptoms, and entities and labels inferred from entire medical dialogues.
    > 
    >  Dataset size: >2000
    > 
    > **[link](http://www.fudan-disc.com/sharedtask/imcs21/index.html)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCL_2021_IMCS.md)**

### CSMI

- ###### 2020

  - PHQC: Classification of public health questions
    > The dataset consists of public health queries categorized into six major themes: diagnosis, treatment, anatomy/physiology, epidemiology, healthy lifestyle, and choosing healthcare providers. Dataset size: 8000.
    > 
    > Dataset size: training set: 5000, test set: 3000
    > 
    > **[link](https://www.heywhale.com/home/competition/5f2d0ea1b4ac2e002c164d82/content)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CSMI_2020_PHQC.md)** | **[paper](https://kns.cnki.net/kcms2/article/abstract?v=5iIAKlsf9WBSHARREy05MZ-PPhK9bEzInxeo5bHu4SeNGafwR3Op2Ed--tzILIXmqQ9wl57xk5efFRWgtS5g7xoFrkEj4jsfkH8RNSqPAdSv1-41GpBnGmXOTgeCaGSQEQqlvyBdbhQuXN_ig_TzgqPWbZ6sViXiFbd_PAt9boYbxvXa_BZevglCeRTpYn7MBKRSkWDnXLxo_aHwSqsY4IEQK9s2cTsgMAnLo6QlZ8kT6QdT3yIxsVuzyB91aRtO&uniplatform=NZKPT&language=CHS)** | **[leaderboard](https://www.heywhale.com/home/competition/5f2d0ea1b4ac2e002c164d82/leaderboard)**

### CCIR

- ###### 2019

  - EMR-Query: Data query-based question answering using electronic health records
    > The dataset consists of query-based question-answer pairs derived from EHRs. Dataset size: NA.
    > 
    > Dataset size: training set: 1800, validation set: 600, test set: 600
    > 
    > **[link](https://www.biendata.xyz/competition/ccir2019/)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/CCIR_2019_EMR-Query.md)** | **[leaderboard](https://www.biendata.xyz/competition/ccir2019/leaderboard/)**




## How to cite

Hui Zong, Rongrong Wu, Jiaxue Cha, Weizhe Feng, Erman Wu, Jiakun Li, Aibin Shao, Liang Tao, Zuofeng Li, Buzhou Tang, Bairong Shen. **Advancing Chinese Biomedical Text Mining with Community Challenges**

## Contact

Hui Zong, West China Hospital of Sichuan University

