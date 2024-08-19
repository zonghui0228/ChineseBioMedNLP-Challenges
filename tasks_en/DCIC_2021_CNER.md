# DCIC 2021 CNER


## 1. Problem Value

The Southeast Liver and Gallbladder Health Big Data Research Institute at Mengchao Hepatobiliary Hospital, Fujian Medical University, is the only independent research and development team within Fujian Province. It has already established a liver disease and liver cancer big data platform, Mengchao Liver Disease Brain, and a series of preliminary applications. The liver disease and liver cancer big data platform aggregates nationwide, multi-center, high-quality liver disease and liver cancer data resources. In 2019, this platform provided the theme and data for "Big Data Liver Cancer Image-Assisted Diagnosis" in the inaugural Digital China Innovation Competition. This year, it once again provided the theme and 2150 cases of data for "Intelligent Medical Decision-Making, Pathological 'Gold Data' Empowering Medical Diagnosis" in the big data track.

This task stems from the actual needs of pathologists at Mengchao Hepatobiliary Hospital. Pathology reports, as the gold standard for diagnosing liver cancer, are crucial references for clinicians in staging and typing liver cancer and are also important research data. Currently, pathology reports are mostly stored as unstructured text descriptions. Due to the involvement of multiple concepts, relationships, and attributes, interpreting them requires specialized medical knowledge. This has led to subpar performance of Natural Language Processing (NLP) in pathology texts. Doctors still manually search for data, which is time-consuming, laborious, and challenging to retrieve key information, thus affecting work efficiency.

## 2. Significance of Solution

The use of NLP in pathology texts has been ineffective, with a key issue being inaccurate named entity recognition (NER). Thus, this task focuses on the application of the fundamental NLP task - Named Entity Recognition (NER) in pathology texts. NER is a fundamental task in NLP and serves as a vital tool for information extraction, question answering systems, syntax analysis, machine translation, and other NLP tasks. The accuracy of NER determines the effectiveness of downstream tasks, making it a crucial foundational problem in NLP. Therefore, this task aims to encourage participating teams to utilize advanced algorithmic techniques, combined with knowledge of pathology medicine, to accurately identify ten named entities including tumor location (Tloc), histological type (This), differentiation degree (Tdiff), tumor count (Tnum), tumor size (Tsize), and microvascular invasion (MVI), thereby enhancing doctors' work efficiency.

## 3. Key Challenges

- The data provided in the task only comes from hospitals, requiring named entity recognition to be carried out on a small sample size.

- Some training data needs to be annotated by participants. This requires participants to refer to relevant medical materials or have team members with medical background knowledge.

- Recognition of ten named entity types covering a wide range, with significant differences in entity magnitudes, and a few entities having low coverage, such as capsule, which is not included in the reference samples.

- Due to variations in doctors' work experience and personal habits, descriptions of the same entity can differ. Some entities have up to twenty different descriptions, further increasing the difficulty of analysis and recognition.