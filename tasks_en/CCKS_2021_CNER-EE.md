# CCKS 2021 CNER-EE

This task is part of a series of evaluations conducted by CCKS focusing on the semantic understanding of Chinese electronic medical records. It builds upon and extends the evaluation tasks from CCKS 2017, 2018, 2019, and 2020. This evaluation continues to emphasize two main tasks: medical named entity recognition and medical event extraction.

Unlike previous years, this evaluation requires participants to provide a solution that addresses both entity recognition and event extraction tasks simultaneously. Participants are encouraged to leverage the relationships between these two tasks during the modeling process to enhance the final performance. Participants are expected to test their solutions on both subtasks, with the overall performance on the test sets of both subtasks determining the final evaluation results.


## Medical Named Entity Recognition

### Task Definition and Description
This task involves Chinese medical entity recognition in medical records. Given a set of plain text electronic medical records, the goal is to identify and extract entity mentions related to medical and clinical fields and categorize them into predefined categories such as diseases, treatments, and examinations.

Compared to the 2020 Named Entity Recognition task, the following adjustments have been made:

Participants are required to perform both entity recognition and event extraction tasks.

#### Formal Definition

##### Input:

- A collection of natural language texts from electronic medical records: 

- Predefined categories: 

##### Output:

- A set of entity mentions and their corresponding categories: 


#### Predefined Categories

Predefined categories are defined as follows:

- Diseases and Diagnosis: Medically defined diseases and a doctor's judgments on causes, pathophysiology, classification, and staging in clinical work.

- Examination: Imaging examinations (X-ray, CT, MR, PETCT, etc.) + contrast studies + ultrasound + electrocardiogram. Excludes diagnostic operations like endoscopy procedures.

- Laboratory Tests: Physical or chemical tests conducted in laboratories, specifically referring to clinical laboratory tests performed by the laboratory department, excluding broad laboratory tests like immunohistochemistry.

- Surgery: Treatments performed by doctors locally on a patient's body, including excisions and sutures, as a primary method of surgery.

- Medication: Specific chemical substances used for disease treatment.

- Anatomical Sites: Refers to anatomical sites where diseases, symptoms, and signs occur in the human body.

### Dataset Description

#### Data Annotation Explanation:

The word list and electronic medical record data are compiled by Yiduyun (Beijing) Technology Co., Ltd.

Annotation data is manually labeled by a professional medical team organized by Yiduyun Company, solely for the CCKS competition evaluation purposes.
Detailed descriptions and annotation specifications of the dataset will be provided along with the data release; they are not reiterated in this task description.

#### Data Example:

```json
{
  "originalText": "Patient underwent rectal cancer radical surgery under general anesthesia in our hospital 3 months ago (DIXON procedure). The surgery went smoothly, and postoperative anti-infection and nutritional support treatment were given to the patient, who recovered well with good wound healing. Postoperative pathology indicated rectal adenocarcinoma (moderately to poorly differentiated), infiltrative ulcerative type, with an area of 3.5*2CM, invading the outer membrane. No cancer was found in the cut ends sent for examination at the proximal and distal ends and at the circumferential base. No cancer was found in the wall lymph nodes (10 nodes in the station, 8 in the middle group). Immunohistochemical staining showed: ERCC1 diffuse (+), TS partially weak (+), SYN (-), CGA (-). After finding no contraindications for chemotherapy, the patient received 3 cycles of chemotherapy, with the regimen as follows: Oxaliplatin 150MG D1, calcium folinate 0.3G + tegafur 1.0G D2-D6, along with leukocyte boosting, liver protection, antiemetic, and immunoenhancement treatment, with mild side effects. The patient's general condition was good during outpatient follow-up, with no nausea, abdominal pain, distension, or discomfort. The patient returned for reevaluation and additional chemotherapy, and was admitted to the outpatient department for 'postoperative rectal cancer.'",
  "entities": [
    {
      "label_type": "Diseases and Diagnosis",
      "overlap": 0,
      "start_pos": 8,
      "end_pos": 11
    },
    {
      "label_type": "Surgery",
      "overlap": 0,
      "start_pos": 21,
      "end_pos": 35
    },
    {
      "label_type": "Diseases and Diagnosis",
      "overlap": 0,
      "start_pos": 78,
      "end_pos": 95
    }
  ]
}
```
#### Dataset Description
For this evaluation, the training data includes:

- 1500 annotated Chinese data samples
- 1000 unannotated Chinese data samples
- A vocabulary list of 6292 Chinese entity words spanning 6 categories

Additionally, 300 annotated data samples will be used as the final evaluation test set. Further details about the dataset will be provided upon its release.


###  Evaluation Metrics

This task employs Precision, Recall, and F1-Measure as evaluation metrics.



## Medical Event Extraction

### Task Definition and Description

This task involves Chinese medical event extraction in electronic medical record texts with the main entity being tumors. The task defines various attributes of tumor events, such as tumor size and primary location, and aims to identify and extract these events and attributes for text structuring.

The task provides a small amount of annotated Chinese data, a large amount of unannotated data sets, and a vocabulary list. The goal is to enhance model performance using methods like unsupervised learning, semi-supervised learning, and transfer learning, given limited training data. This approach aims to simulate scenarios closer to real-world applications.

#### Event Template Definition

Event Main Entity: Tumor

Attribute 1: Primary Location [The tissue or organ where a certain disease first occurs]

Attribute 2: Lesion Size [The size of the primary location]

Attribute 3: Metastasis Location [The other tissues or organs to which a certain disease spreads from the primary site]

Each text may contain zero or multiple attribute entities, such as multiple primary locations.


### Dataset Description

#### Data Annotation Details

The electronic medical record data is authored by Medicus-AI (Beijing) Technology Co., Ltd. The annotated data is manually labeled by a professional medical team organized by Medicus-AI and is intended for evaluation purposes in the CCKS competition.

Detailed descriptions and annotation guidelines for the dataset will be provided alongside the data release. Further explanations will not be reiterated in this task description.

#### Data Samples

Original Text: [Chinese text excerpt provided]

Tumor Primary Location: Right upper lobe of the lung

Primary Lesion Size: 12mm×8mm

Metastasis Location: Left supraclavicular area, multiple lymph nodes in the mediastinum


#### Dataset Description

The training data for this evaluation includes:

- 1400 annotated Chinese data entries
- 1300 unannotated Chinese data entries
- 863 Chinese entity vocabulary entries

Additionally, this evaluation will employ 300 annotated data entries as the final evaluation test set. Detailed descriptions of the dataset will also be provided along with the data release.

### Evaluation Metrics

Since each text may contain multiple attribute entities for a single event property, the evaluation metrics use attribute entities instead of attributes to calculate precision and recall. The F1 score of attribute entities will be used as the evaluation metric.

## Result Evaluation Method

The test results for the tasks of medical entity recognition and medical event extraction will be weighted and summed according to specific weights. Both subtasks will be assigned a weight of 0.5 for the final evaluation.











