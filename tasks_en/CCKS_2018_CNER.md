# CCKS 2018 CNER


This task is jointly organized by the Knowledge Engineering Laboratory of Tsinghua University and MedWhatever Cloud (Beijing) Technology Co., Ltd. It is an improvement and enhancement of the CNER evaluation at CCKS 2017. Under the guidance and participation of a professional medical team, starting from specific clinical applications, a more challenging medical entity recognition task with higher quality annotations is built on brand-new electronic medical record data. It is the first step in a series of evaluation competitions focused on the semanticization of Chinese electronic medical records, laying a solid foundation for upcoming tasks such as medical entity structuring, medical entity standardization, and medical entity relationship extraction.

## Task Definition and Description

This evaluation task focuses on named entity recognition in Chinese electronic medical records. Specifically, given a set of electronic medical record plain text documents, the goal of the task is to identify and extract entity mentions related to medical clinical practices and classify them into predefined categories such as symptoms, medications, surgeries, etc.



### Formal Definition:

**Input:**

- A collection of natural language texts of electronic medical records.

- Predefined categories.

**Output:**

A set of pairs consisting of entity mentions and their corresponding categories.


### Entity Category Definition:

Taking into account the content and characteristics of the data source "history of present illness records," this task focuses on three major categories of entities: symptoms, medications, and surgeries. Since symptom-type entities often appear in structured forms, symptoms are further refined into three subcategories: anatomical location (the subject of complex symptoms), symptom description (the description of complex symptoms), and independent symptoms. The predefined categories for this task are limited to the following five types:

- Anatomical location: A structural unit composed of various tissues capable of performing functions, for example, "abdomen."

- Symptom description: Refers to the patient's own experience and sensation of physiological function abnormalities after falling ill, which needs to be output in conjunction with anatomical locations; for example, "discomfort," which should be combined with "abdominal" to output "abdominal discomfort."

- Independent symptom: Refers to the patient's own experience and sensation of physiological function abnormalities after falling ill, which can be output independently, for example, "dizziness."

- Medication: A chemical substance used to treat, prevent, or promote health.

- Surgery: Refers to the cutting, suturing, or other treatments performed by a doctor on a patient's body using medical instruments.



## Data and Annotation Instructions:

The dataset used for this task is provided by MedWhatever Cloud (Beijing) Technology Co., Ltd., and a professional team of doctors has organized and annotated the data specifically for the CCKS 2018 competition evaluation.

Electronic medical records mainly consist of outpatient records and inpatient records. Outpatient records are usually shorter, contain less information, and lack tracking of the patient's treatment progress. Therefore, this task focuses solely on inpatient records. Inpatient records include admission records, progress notes, medical orders, diagnostic reports, pathology data, etc. The admission record documents the information obtained by the attending physician through inquiries, physical examinations, and auxiliary tests after the patient's admission. Specific content includes general items, chief complaints, present illness history, past medical history, personal history, family history, menstrual and obstetric history, physical examinations, auxiliary examinations, diagnosis, etc. Among these, the present illness history is a key component of inpatient records, focusing on understanding the occurrence, evolution, and diagnosis and treatment process of the patient's current illness, containing richer medical information. Therefore, this evaluation primarily focuses on identifying and extracting medical named entities from the present illness history section.

The dataset is divided into a training set and a test set. Due to the complexity of medical data, especially electronic medical record data, and the challenging nature of annotation work, the annotated data will be released gradually in batches. The initial plan is to release 600 present illness documents as the training set and 200-400 documents as the test set.


## Evaluation Metrics:

In this task, precision, recall, and F1-Measure are used as evaluation metrics.










