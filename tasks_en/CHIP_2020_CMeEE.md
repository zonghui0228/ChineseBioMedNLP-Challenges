# CHIP 2020 CMeEE


## Task Introduction

The task involves Named Entity Recognition (NER) in Chinese medical texts. NER is a crucial subtask of information extraction that has seen significant progress in recent years. Medical texts like medical textbooks, medical encyclopedias, clinical cases, medical journals, admission records, and laboratory reports contain a wealth of medical knowledge and terminology. By combining entity recognition technologies with the medical domain, machine reading of medical texts can significantly enhance the efficiency and quality of clinical research, benefiting downstream tasks. Teaching machines to "understand" medical data involves accurately extracting key information from vast amounts of medical texts, which involves natural language processing techniques like named entity recognition and relation extraction. Unstructured texts in the medical field are composed of Chinese natural language sentences or collections of sentences. Entity extraction involves identifying medical entities such as diseases and symptoms from unstructured medical texts.

## Task Details
This evaluation task focuses on Named Entity Recognition in Chinese medical texts. Given a schema and a sentence, the goal is to identify and extract entities related to clinical medicine from a set of purely medical text documents and classify them into pre-defined categories. Medical text entities are divided into nine major categories: diseases, clinical symptoms, drugs, medical equipment, medical procedures, body parts, medical tests, microorganisms, and departments. Before annotation, the articles are automatically segmented into words, and all medical entities are correctly segmented.

Basic principles of Named Entity Annotation:

- The "clinical symptoms" entity category allows nesting, meaning other eight categories of entities can exist within it.

- For medical entities other than "clinical symptoms," the "maximum unit annotation method" is followed. This means if an entity category contains other entities, only the largest entity needs to be annotated without nesting.

- To ensure the comprehensibility and completeness of medical entity meanings, the nine entity classes can contain necessary punctuation. An entity can be a word, phrase, or sentence.

### Input/Output:

**Input:** Sentence

**Output:** Positions and types of medical entities contained in the sentence



## Dataset Introduction

The dataset used in this competition was jointly constructed by the Key Laboratory of Computational Linguistics, Ministry of Education, Peking University, the Natural Language Processing Laboratory of the School of Information Engineering, Zhengzhou University, Harbin Institute of Technology (Shenzhen), and the Smart Healthcare Research Group of the Artificial Intelligence Research Center of Peng Cheng Lab. The total word count reaches 2.2 million, including 47,194 sentences, 938 files, with an average of 2,355 words per file. The dataset comprises nine major categories of medical entities, including 504 common pediatric diseases, 7,085 body parts, 12,907 clinical manifestations, and 4,354 medical procedures.

Sentences record source texts, marking the positions and labels of medical entities, with four spaces separating the positions and labels of the medical entities. In this example, clinical manifestation entities nest body entities. "Respiratory muscle paralysis" and "respiratory center involvement" are clinical manifestation entities, with nested "respiratory muscle" and "respiratory center" body entities respectively.

"Patients with respiratory muscle paralysis and respiratory center involvement may develop pneumonia, atelectasis, etc. due to impaired breathing. |||0 2 bod|||0 4 sym|||6 9 bod|||6 11 sym|||15 18 sym|||22 23 dis|||25 27 dis|||"

The table below shows the tagging scheme and examples of entities. The corpus in the dataset comes from clinical pediatrics, and the dataset is divided as follows: training set (15,000), validation set (5,000), test set Test1 (3,000), and test set Test2 (3,618). The training set is for training purposes and is freely downloadable. The test set is divided into two parts, Test1 for participants to independently verify on the platform, while Test2 will be released one week before the end of the competition and cannot be independently verified on the platform. Test2 will be used for the final evaluation and ranking.



## Evaluation Metrics

Participants' SPO (Subject-Predicate-Object) results on the test set will be compared with the annotated results on the test set for precise matching. The evaluation will be based on F1 score, macro-average, and micro-average metrics.













