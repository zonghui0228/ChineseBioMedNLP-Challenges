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

### CCKS

- ###### 2023
  - PromptCBLUE: CCKS-PromptCBLUE medical large model evaluation
    > The dataset is sourced from the CBLUE benchmark, encompassing 16 scenarios of medical natural language processing tasks, and includes 94 instruction fine-tuning templates.
    > 
    > Training set: 68500, validation set: 10270, test set: 20540
    > 
    > **[link](https://sigkg.cn/ccks2023/evaluation)** | **[link_en](https://github.com/zonghui0228/ChineseBioMedNLP-Challenges/blob/master/tasks_en/ccks_2023_PromptCBLUE.md)** | **[paper](https://arxiv.org/abs/2310.14151)** | **[github](https://github.com/michael-wzhu/PromptCBLUE/blob/main/README_EN.md)**

- ###### 2021

  - CNER-EE: Entity and event extraction of Chinese electronic medical records
    > The medical named entity recognition dataset consists of manually annotated plain text documents from EHRs, identifying medically relevant entities. It includes 6 predefined categories: diseases and diagnoses, examinations, tests, surgeries, medications, and anatomical locations. The medical event extraction dataset includes manually annotated plain text documents from EHRs, focusing on attribute entities related to primary entities of tumor events. It encompasses 3 categories: primary site, lesion size, and metastatic site.
    > 
    > 2800 and 3000
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** **[link_en](#)** **[paper](#)**

  - Phe-Drug-Mol: Link Prediction of Phenotype-Drug-Molecular Multilevel Knowledge Graph
    > A knowledge graph constructed from structured data sourced from reputable websites encompasses 7 types of relationships: associated_with, disease_mapped_to_gene, treats, targets, interacts_with, annotates, and pathway_has_gene_element. 
    > 
    > 80,000 entities, 1,200,000 triples.
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** **[link_en](#)** **[paper](#)**

  - MedDG: Chinese Medical Dialogue Generation Incorporating Implicit Entities
    > The MedDG dataset, annotated with entities, encompasses 12 types of gastroenterology-related diseases. Each dialogue is annotated with 160 relevant entities across 5 categories: diseases, symptoms, attributes, examinations, and medications. Dataset size: 20,611.
    > 
    > Training set: 17864, test set: 4347
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** **[link_en](#)** **[paper](#)**

  - CMRC: Reading Comprehension for Chinese Medical Popular Science Knowledge
    > The dataset for reading comprehension of medical popular science knowledge includes the main content and a list of question-answer pairs, including question description, question ID, answer list. The dataset of recognizing irrelevant answers in medical popular science knowledge, the format of this dataset is one entry per line, with five columns, including Label, Docid, Question, Description, and Answer.
    > 
    > 36000 and 55000
    > 
    > **[link](https://sigkg.cn/ccks2021/?page_id=27)** **[link_en](#)** **[paper](#)**

- ###### 2020

  - Covid19: Construction and Question-Answering of COVID-19 Knowledge Graph
    > The COVID-19 knowledge graph encompasses seven entity types: virus, bacteria, disease, drug, medical specialty, examination subject, and symptom. The COVID-19 concept graph additionally includes type relationships between entities and concepts, as well as hierarchical relationships among concepts. The antiviral drug graph includes entities, entity attributes, and relationships between entities. The integrated dataset from the open-domain knowledge base PKUBASE and the OpenKG COVID-19 special topic includes information on entity category triples, hierarchical relationships between types, and predicates. 
    > 
    > This knowledge graph contains 66,499,920 triples, 25,574,536 entities, and 408,690 relations. A training set of 4,000 items, a validation set of 1,529 items, and a test set of 1,599 items
    > 
    > **[link](https://sigkg.cn/ccks2020/?page_id=516)** **[link_en](#)** **[paper](#)**

  - CNER-EE: Entity and event extraction of Chinese electronic medical records
    > For medical named entity recognition dataset, it consists of manually annotated entities in EHRs, including diseases and diagnoses, examinations, tests, surgeries, medications, and anatomical locations. For medical event extraction dataset, it comprises manually annotated attribute entities associated with primary entities of oncology events in EHRs. It includes three categories: primary site, lesion size, and metastatic site.
    > 
    > 1500
    > 
    > **[link](https://sigkg.cn/ccks2020/?page_id=516)** **[link_en](#)** **[paper](#)**

- ###### 2019

  - CNER-AE: Named entity recognition and attribute extraction for electronic health records
    > Medical Named Entity Recognition Dataset: The dataset comprises manually annotated documents from EHRs, capturing clinically relevant entities. These entities are categorized into 5 pre-defined categories: Symptoms and Signs, Examinations and Tests, Diseases and Diagnoses, Treatments, and Body Parts. Dataset size: 12,020. Attribute Extraction Dataset: This dataset consists of manually annotated documents from EHRs, focusing on attribute entities related to tumor events. These entities are categorized into 3 types: Lesion Size, Primary Site, and Metastatic Site. Dataset size: 2,000.
    > 
    > 1379
    > 
    > **[link](https://www.sigkg.cn/ccks2019/?page_id=62)** **[link_en](#)** **[paper](#)**

- ###### 2018

  - CNER: Named entity recognition for electronic health records
    > The dataset consists of manually annotated entities from EHRs, including anatomical sites, symptom descriptions, independent symptoms, medications, and surgeries.
    > 
    > 800
    > 
    > **[link](https://www.sigkg.cn/ccks2018/?page_id=1)** **[link_en](#)** **[paper](#)**

- ###### 2017

  - CNER: Named entity recognition for electronic health records
    > The dataset consists of manually annotated entities from EHRs, including anatomical locations, symptom descriptions, independent symptoms, medications, and surgeries.
    > 
    > 400
    > 
    > **[link](https://www.sigkg.cn/ccks2017/?page_id=51)** **[link_en](#)** **[paper](#)**


### CHIP

- ###### 2023
  - PromptCBLUE: CHIP-PromptCBLUE medical large model evaluation
    > The dataset is sourced from the CBLUE benchmark, encompassing 18 scenarios of medical natural language processing tasks, and includes over 450 instruction fine-tuning templates.
    > 
    > Training set: 87100, validation set: 8456, test set: 8456
    > 
    > **[link](http://cips-chip.org.cn/2023/eval1)** **[link_en](#)** **[paper](https://link.springer.com/chapter/10.1007/978-981-97-1717-0_1)**

  - NER: Chinese medical text few-shot named entity recognition evaluation
    > The dataset comprises manually annotated entities relevant to medical clinical contexts within medical texts. It includes 15 labels: item, sociology, disease, etiology, body, age, adjuvant, therapy, electroencephalogram, equipment, drug, procedure, treatment, microorganism, department, epidemiology, symptom, and others.
    > 
    > Training set: 400, validation set: 100, test set: 100
    > 
    > **[link](http://cips-chip.org.cn/2023/eval2)** **[link_en](#)** **[paper](#)**

  - MedOCR: Drug paper document recognition and entity relation extraction
    > The drug leaflets were manually annotated for drugs, diseases, and clinical findings.
    > 
    > Training set: 400, validation set: 200, test set: 400
    > 
    > **[link](http://cips-chip.org.cn/2023/eval3)** **[link_en](#)** **[paper](#)**

  - YIER-LLM: CHIP-YIER medical large model evaluation task
    > A series of multiple-choice questions constructed from medical entrance exam questions, clinical practice physician assessments, medical textbooks, medical literature/guidelines, and publicly available medical records. Dataset size: 1500.
    > 
    > Training set: 1000, test set: 500
    > 
    > **[link](http://cips-chip.org.cn/2023/eval4)** **[link_en](#)** **[paper](#)**

  - PICOS: Medical literature PICOS identification
    > The dataset consists of titles and abstracts from medical publications, annotated with five categories: Population (P), Intervention (I), Comparison (C), Outcome (O), and Study Types (S)
    > 
    > Training set: 2500, validation set: 1000, test set: 1000
    > 
    > **[link](http://cips-chip.org.cn/2023/eval5)** **[link_en](#)** **[paper](#)**

  - DTC: Chinese diabetes question classification evaluation
    > The dataset consists of diabetes questions from internet, encompassing six categories: diagnosis, treatment, common knowledge, healthy lifestyle, epidemiology, and others.
    > 
    > Training set: 6000, validation set: 1000, test set: 1000
    > 
    > **[link](http://cips-chip.org.cn/2023/eval6)** **[link_en](#)** **[paper](#)**

- ###### 2022

  - AGAC: Text mining task for gene-disease association semantics
    > The AGAC corpus comprises 12 categories of molecular entities related to "gene-disease" associations and their triggering term entities: Var, MPA, Interaction, Pathway, CPA, Reg, PosReg, NegReg, Disease, Gene, Protein, and Enzyme. It includes semantic role annotations: ThemeOf and CauseOf; regulatory types: Loss of Function (LOF), Gain of Function (GOF), Regulation (REG), and Composite changes in function (COM).
    > 
    > Training set: 250, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval1)** **[link_en](#)** **[paper](#)**

  - CMedCausal: Medical causal entity and relation extraction
    > The annotated dialogue corpus includes three types of relationships: "causal", "conditional", and "hyponymy"
    > 
    > Training set: 2000, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval2)** **[link_en](#)** **[paper](#)**

  - Text2DT: Extracting medical decision trees from medical texts
    > The dataset consists of extracted diagnostic and therapeutic decision trees from clinical practice guidelines and medical textbooks. A diagnostic and therapeutic decision tree is defined as a binary tree composed of conditional nodes and decision nodes.
    > 
    > Training set: 300, validation set: 100, test set: 100
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval3)** **[link_en](#)** **[paper](#)**

  - MedOCR: Identification of electronic medical paper documents
    > The dataset consists of scanned images of paper medical records from the internet, defining 87 attributes to be extracted, which include types such as discharge summaries; outpatient invoices; pharmacy purchase invoices; and hospitalization invoices.
    > 
    > Training set: 1000, validation set: 200, test set: 500
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval4)** **[link_en](#)** **[paper](#)**

  - CDN: Clinical diagnostic coding
    > The dataset comprises annotated information extracted from EHRs, including diagnostic details (such as admission diagnosis, preoperative diagnosis, postoperative diagnosis, and discharge diagnosis), as well as surgical names, medication names, and medical order names.
    > 
    > Training set: 2700, test set: 337
    > 
    > **[link](http://www.cips-chip.org.cn/2022/eval5)** **[link_en](#)** **[paper](#)**

- ###### 2021

  - MDCFNPC: Classifying positive and negative clinical findings in medical dialog
    > The data comes from publicly available internet-based telemedicine consultations includes patient chief complaints and physician diagnostic judgments, categorized into four attributes: negative, positive, other, and unspecified.
    > 
    > Training set: 6000, validation set: 2000, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn/2021/eval1)** **[link_en](#)** **[paper](#)**

  - CDEE: Event extraction of clinical discovery
    > The dataset extracted present medical history or imaging findings reports from EHRs, involving attributes across four dimensions: anatomical sites, main terms, descriptive terms, and occurrence status.
    > 
    > Training set: 2070, test set: 532
    > 
    > **[link](http://www.cips-chip.org.cn/2021/eval2)** **[link_en](#)** **[paper](#)**

  - CDN: Normalization of Chinese clinical terminology
    > The dataset comprises diagnostic entities, partial surgical entities, and standardized surgical relationship corpora extracted from Chinese EHRs. Dataset size: NA.
    > 
    > Training set: 9699, test set: 801
    > 
    > **[link](http://www.cips-chip.org.cn/2021/eval3)** **[link_en](#)** **[paper](#)**

- ###### 2020

  - CMeEE: Chinese medical text named entity recognition
    > The dataset comprises 9 entity types extracted through medical text mining: diseases, clinical manifestations, medications, medical devices, medical procedures, anatomical structures, medical laboratory tests, microorganisms, and departments.
    > 
    > Training set: 15000, validation set: 5000, test set: 6618
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval1)** **[link_en](#)** **[paper](#)**

  - CMeIE: Chinese medical text relationship extraction
    > The pediatric training corpus and the corpus extracted from a hundred common diseases yielded 53 schemas, comprising 10 synonymous relations and 43 other relations.
    > 
    > Training set: 17924, validation set: 4482, test set: 5602
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval2)** **[link_en](#)** **[paper](#)**

  - CDN: Clinical terminology normalization
    > The dataset includes diagnostic entities extracted from Chinese EHRs.
    > 
    > Training set: 8000, test set: 10000
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval3)** **[link_en](#)** **[paper](#)**

  - Covid19: Prediction of epidemic trends in COVID-19
    > The dataset comprises regional time-series data of confirmed COVID-19 cases, including daily counts of newly diagnosed cases.
    > 
    > nan
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval4)** **[link_en](#)** **[paper](#)**

  - TCM-QA: Question generation of traditional Chinese medicine literature
    > Texts from the field of Traditional Chinese Medicine (TCM), including four TCM books and selected texts from TCM forums, with manually constructed question-answer pairs.
    > 
    > Training set: 3500, validation set: 750, test set: 750
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval5)** **[link_en](#)** **[paper](#)**

  - TCM-NER: Entity recognition in traditional Chinese medicine instructions
    > The dataset comprises 13 types of entities extracted from traditional Chinese medicine drug instructions: DRUG, DRUG_INGREDIENT, DISEASE, SYMPTOM, SYNDROME, DISEASE_GROUP, FOOD, FOOD_GROUP, PERSON_GROUP, DRUG_GROUP, DRUG_DOSAGE, DRUG_TASTE, and DRUG_EFFICACY.
    > 
    > Training set: 1200, validation set: 400, test set: 397
    > 
    > **[link](http://www.cips-chip.org.cn/2020/eval6)** **[link_en](#)** **[paper](#)**

- ###### 2019

  - CDN: Clinical terminology normalization
    > The dataset consists of real surgical entities extracted from Chinese electronic medical records that require standardization.
    > 
    > Training set: 4000, validation set: 1000, test set: 2000
    > 
    > **[link](http://www.cips-chip.org.cn:8000/evaluation)** **[link_en](#)** **[paper](#)**

  - STS: Disease question-answering based on transfer learning
    > The dataset comprises extracted online disease question-answer sentence pairs related to diabetes, hypertension, hepatitis, aids, and breast cancer.
    > 
    > Training set: 20000, validation set: 10000, test set: 50000
    > 
    > **[link](http://www.cips-chip.org.cn:8000/evaluation)** **[link_en](#)** **[paper](#)**

  - CTC: Text classification of Chinese clinical trials eligibility criteria
    > Descriptive sentences of Chinese clinical trial inclusion/exclusion criteria, and a predefined set of 44 semantic categories for these criteria.
    > 
    > Training set: 22962, validation set: 7682, test set: 7697
    > 
    > **[link](http://www.cips-chip.org.cn:8000/evaluation)** **[link_en](#)** **[paper](#)**

- ###### 2018

  - CNER-AE: Entity and attribute extraction of Chinese electronic medical records
    > Imaging examination reports related to lung cancer and breast cancer.
    > 
    > Training set: 600, test set: 200
    > 
    > **[link](http://icrc.hitsz.edu.cn/chip2018/Task.html)** **[link_en](#)** **[paper](#)**

  - STS: Patient health consultation question pairs matching
    > The dataset comes from real patient health consultation corpus. Given two sentences, it is required to determine whether the intentions are the same or similar.
    > 
    > Training set: 20000, test set: 10000
    > 
    > **[link](http://icrc.hitsz.edu.cn/chip2018/Task.html)** **[link_en](#)** **[paper](#)**

### DCIC

- ###### 2021

  - CNER: Medical entity recognition based on pathology report text
    > Extracted 10 types of entities from pathological text.
    > 
    > Training set: 1000, test set: 1050
    > 
    > **[link](https://www.datafountain.cn/competitions/498)** **[link_en](#)** **[paper](#)**

### CCL

- ###### 2021

  - IMCS: Intelligent medical dialogue diagnosis and evaluation
    > The dataset consists of dialogue cases from online medical consultation platforms, utilized for entity recognition, simulated dialogues, and disease diagnosis. Each sample in the dataset includes disease category, patient self-description text, symptoms, and entities and labels inferred from entire medical dialogues.
    > 
    >  >2000
    > 
    > **[link](http://www.fudan-disc.com/sharedtask/imcs21/index.html)** **[link_en](#)** **[paper](#)**

### CSMI

- ###### 2020

  - PHQC: Classification of public health questions
    > The dataset consists of public health queries categorized into six major themes: diagnosis, treatment, anatomy/physiology, epidemiology, healthy lifestyle, and choosing healthcare providers. Dataset size: 8000.
    > 
    > Training set: 5000, test set: 3000
    > 
    > **[link](https://www.heywhale.com/home/competition/5f2d0ea1b4ac2e002c164d82/content)** **[link_en](#)** **[paper](#)**

### CCIR

- ###### 2019

  - EMR-Query: Data query-based question answering using electronic health records
    > The dataset consists of query-based question-answer pairs derived from EHRs. Dataset size: NA.
    > 
    > Training set: 1800, validation set: 600, test set: 600
    > 
    > **[link](http://ir.fzu.edu.cn/ccir2019/test.html)** **[link_en](#)** **[paper](#)**




## How to cite

Hui Zong, Rongrong Wu, Jiaxue Cha, Weizhe Feng, Erman Wu, Jiakun Li, Aibin Shao, Liang Tao, Zuofeng Li, Buzhou Tang, Bairong Shen. **Advancing Chinese Biomedical Text Mining with Community Challenges**

## Contact

Hui Zong, West China Hospital of Sichuan University