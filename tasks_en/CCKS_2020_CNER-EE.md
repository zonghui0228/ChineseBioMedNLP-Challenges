# CCKS 2020 CNER-EE

This task is a continuation of a series of evaluations conducted by CCKS on the semanticization of Chinese electronic medical records. Building upon the related evaluation tasks of CCKS 2017, 2018, and 2019, this task has been extended and expanded.

This task consists of two subtasks:

- Medical Named Entity Recognition

- Medical Event Extraction

Participants can choose to compete in both subtasks simultaneously, or they can choose to compete in either subtask individually.


## Medical Named Entity Recognition

### 1. Task Definition and Description

This task involves the recognition of medical entities within Chinese medical records. Given a set of electronic medical record plain text documents, the goal is to identify and extract mentions of entities related to clinical medicine (entity mentions). These mentions are then categorized into predefined classes, such as diseases, treatments, and examinations, among others.
Compared to the 2019 named entity recognition task, the following adjustments have been made:

- a. Annotated new data to expand the training dataset.
- b. Provided entity dictionaries and a large amount of unlabeled data for participants to use.



#### 1.1 Formal Definition:
**Input:**

- Collection of natural language texts from electronic medical records

- Predefined categories

**Output:**

- Set of entity mentions and their corresponding categories


#### 1.2 Predefined Categories:

- Disease and Diagnosis: Diseases defined in medicine and judgments made by doctors in clinical work on etiology, pathophysiology, classification, and staging.

- Examination: Imaging examinations (X-rays, CT scans, MRIs, PET-CT scans, etc.) + contrast studies + ultrasound + electrocardiograms. Excludes diagnostic procedures such as endoscopy and colonoscopy to avoid excessive overlap with surgical procedures.

- Test: Physical or chemical examinations conducted in the laboratory, specifically referring to clinical laboratory tests performed by the laboratory department in clinical practice, excluding broader laboratory tests like immunohistochemistry.

- Surgery: Treatment performed by doctors locally on the patient's body, involving excision, suturing, etc., being the primary treatment method in surgery.

- Medication: Specific chemical substances used for disease treatment.

- Anatomical Site: Refers to the anatomical location in the human body where diseases, symptoms, and signs occur.

### 2. Dataset Description

#### 2.1 Data Annotation Explanation

The vocabulary and electronic medical record data were compiled by MedDyTech (Beijing) Technology Co., Ltd. The annotated data was manually labeled by a professional medical team organized by MedDyTech and is solely for use in the CCKS competition evaluations.

#### 2.2 Data Example

```json
{
  "originalText": "患者3月前因“直肠癌”于在我院于全麻上行直肠癌根治术（DIXON术），手术过程顺利，术后给予抗感染及营养支持治疗，患者恢复好，切口愈合良好。，术后病理示：直肠腺癌（中低度分化），浸润溃疡型，面积3.5*2CM，侵达外膜。双端切线另送“近端”、“远端”及环周底部切除面未查见癌。肠壁一站（10个）、中间组（8个）淋巴结未查见癌。，免疫组化染色示：ERCC1弥漫（+）、TS少部分弱（+）、SYN（-）、CGA（-）。术后查无化疗禁忌后给予3周期化疗，，方案为：奥沙利铂150MG D1，亚叶酸钙0.3G+替加氟1.0G D2-D6，同时给与升白细胞、护肝、止吐、免疫增强治疗，患者副反应轻。院外期间患者一般情况好，无恶心，无腹痛腹胀胀不适，无现患者为行复查及化疗再次来院就诊，门诊以“直肠癌术后”收入院。"
  "entities": [
    {
      "label_type": "疾病和诊断",
      "overlap": 0,
      "start_pos": 8,
      "end_pos": 11
    },
    {
      "label_type": "手术",
      "overlap": 0,
      "start_pos": 21,
      "end_pos": 35
    },
    {
      "label_type": "疾病和诊断",
      "overlap": 0,
      "start_pos": 78,
      "end_pos": 95
     }
  ]
}
```

#### 2.3 Dataset Description

For this evaluation, the training data includes:

- 1500 annotated records
- 1000 unannotated records
- A vocabulary of 6292 entity terms across 6 categories

Statistics of the annotated dataset are presented in the table below:

|          | Text  | Disease & Diagnosis | Examination | Test  | Surgery | Medication | Anatomical Site | Total |
|----------|-------|----------------------|-------------|-------|---------|------------|-----------------|-------|
| Training | 1500  | 6211                 | 1490        | 1885  | 1327    | 2841       | 12660           | 26414 |


### 3. Evaluation Metrics

This task employs Precision, Recall, and F1-Measure as evaluation metrics.



## Medical Event Extraction

### 1. Task Definition and Description
This task involves the extraction of medical events from Chinese medical records, specifically focusing on electronic medical record text data with the primary entity being tumors. The task defines various attributes of tumor events, such as tumor size and primary tumor site, aiming to identify and extract these events and attributes for text structuring.

This task provides a small amount of annotated data, a large amount of unannotated data sets, and vocabularies, with the goal of leveraging unannotated texts and semi-supervised methods to improve model performance in situations where training data is limited. This approach aims to be closer to real-world scenarios.

#### 1.1 Event Template Definition

Main Entity: Tumor

Attribute 1: Primary Site [The tissue or organ where a certain disease initially occurs]

Attribute 2: Lesion Size [The size of the primary site]

Attribute 3: Metastasis Site [The other tissue or organ to which a disease spreads from the initial site]

Each text may have zero or multiple instances of each attribute entity, such as multiple primary sites.


### 2. Dataset Description

#### 2.1 Data Annotation Explanation

The vocabulary and electronic medical record data were compiled by MedDyTech (Beijing) Technology Co., Ltd. The annotated data was manually labeled by a professional medical team organized by MedDyTech and is solely for use in the CCKS competition evaluations.

#### 2.2 Data Example


- 原文：右肺癌化疗后，对比2016-11-29CT： 右上肺病变较前范围稍缩小，周边少许炎症较前稍减少。 两肺散在小结节，大致同前。 左侧锁骨下区、纵隔多发淋巴结，考虑转移，较前稍缩小。 肝囊肿。 左肾小囊肿。右肺癌化疗后，对比2016-11-29CT： 右肺上叶见不规则结节状、片状病灶，边界不清，最大层面大小约12mm×8mm，边缘呈分叶状，增强扫描不均匀强化，紧贴斜裂胸膜，部分范围较前略缩小，右上肺见少许斑片状稍高密度影，边界不清，较前明显减少。左下肺（se8，im96）、左上肺（se8，im221）及右下肺（se8，im104）散在数个小类结节，边界清，大者直径3mm，大致同前。 右肺上叶前内基底段支气管变窄，基底段支气管分支管壁增厚，气管及其余支气管分支通畅。 左侧锁骨下区、两下上气管旁、血管前、主动脉弓旁、主肺动脉窗、隆突上见多发淋巴结，部分相互融合，大者短径约5mm，轻度强化，较前稍缩小。 两侧胸腔未见积液，左侧胸膜未见明显增厚。心包未见明显积液。 肝脏形态正常，各叶比例在正常范围以内，其外形轮廓光整，肝内见多个低密度灶，边界清，大者直径约9mm，未见强化。 肝内胆管正常，其内未见结石影，胆囊大小正常，其内未见结石影，胆总管未见扩张，其内未见结石影。肝门区正常。门静脉未见异常。   脾大小正常，密度均匀。胰腺大小、形态正常，密度均匀。  左肾见低密度灶，边界清，大小约4mm×3mm，未见强化。 右肾及两肾下腺未见异常。  膈脚后、腹主动脉旁未见肿大淋巴结。 扫描范围未见骨质破坏征象。
- 肿瘤原发部位：右肺上叶
- 原发病灶大小： 12mm×8mm
- 转移部位：左侧锁骨下区、纵隔多发淋巴结


#### 2.3 Dataset Description

For this evaluation, the training data consists of:

- 1) 1400 annotated records
- 2) 1300 unannotated records.
- 3) A vocabulary of 863 entity terms.

The statistics of the annotated dataset are presented in the following table.

|         | Text  | Primary Tumor Site | Lesion Size | Metastasis Site | Total |
|---------|-------|--------------------|-------------|-----------------|-------|
| Training| 1400  | 1209               | 590         | 1013            | 2812  |


### 3. Evaluation Metrics

Since each text may have multiple attribute entities for an event attribute, the evaluation metrics use attribute entities instead of attributes to calculate precision and recall. Finally, the F1 value of attribute entities is used as the evaluation metric.








