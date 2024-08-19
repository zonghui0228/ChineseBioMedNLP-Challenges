# CHIP 2022 CDN


## Task Overview

Disease classification and surgical operation classification coding is the process of processing patient disease diagnosis and treatment information, and is an important link in medical record information management. Coding of medical records has become one of the important bases for hospital scientific and informational management. It is increasingly widely and deeply applied in evaluating medical quality and efficiency, designing clinical pathways, evaluating key disciplines, hospital reviews, disease diagnosis grading, infectious disease reporting, medical payments, rational drug use monitoring, and other aspects.
Among the various classification schemes, the most influential and widely used worldwide is the International Classification of Diseases (ICD). ICD is an internationally unified disease classification method developed by the WHO and is currently the internationally accepted disease classification method. China has also introduced the National Clinical Edition 2.0 of Disease Classification and Code and the National Clinical Edition 2.0 of Surgical Operation Classification Code, which have been applied in some hospitals.


## Task Details

The main goal of this evaluation task is to code diagnoses in Chinese electronic medical records. Given relevant diagnostic information for a single medical visit (including admission diagnosis, preoperative diagnosis, postoperative diagnosis, discharge diagnosis), as well as the names of surgeries, drugs, and orders, the requirement is to provide the corresponding National Clinical Edition 2.0 standard terms. All visit data is derived from real medical data and annotated according to the "National Clinical Edition 2.0 of Disease Classification and Code" vocabulary. An example is as follows:
Where "target" represents the code, with multiple codes separated by ";".


| Discharge Diagnosis      | Surgery Name                                                                                | Preoperative Diagnosis      | Postoperative Diagnosis     | Admission Diagnosis       | Drug Name                                        | Doctor's Orders                                                                                                     | Target                                             |
|--------------------------|---------------------------------------------------------------------------------------------|-----------------------------|-----------------------------|--------------------------|-------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|
| Right renal carcinoma pt2an0m0 Hypertension | Partial right nephrectomy via laparotomy + additional charge for AI-assisted treatment (SI) | Bilateral renal tumors      |                               | Right renal carcinoma Hypertriglyceridemia Hyperuricemia Hypertension | Omega-3 fish oil fat emulsion Acetylcarnitine Lactulose Diazepam Celecoxib ... | 3M breathable transparent dressing (fixation catheter) 9546hp 10*11.5cm. CT scan (spiral scan) Disposable oxygen tube ot-mi-100 (small size) ... | Renal malignant tumor; Primary hypertension |
| Esophagogastric junction cancer pt4an3bm1 Stage IV | Laparoscopic-assisted radical surgery for cardia cancer (cardia cancer resection + D2 lymph node dissection + esophagointestinal R-Y anastomosis) + liver nodule resection | Esophagogastric junction mass with gastrointestinal bleeding | Esophagogastric junction mass with gastrointestinal bleeding | Severe anemia Esophagogastric junction cancer ct3n2m0 | Omega-3 fish oil fat emulsion Acetylcarnitine Medium/long chain fat emulsion (C8-24) Furosemide Diazepam ... | Infusion connector (Kelfo) 01c-c3300 (Kelfo): 100 per box 3M transparent dressing (fixation catheter) (Minnesota) 1679 10*11.5cm 3M breathable transparent dressing (fixation catheter) 9546hp 10*11.5cm. CVC care Integrated oxygen tube (Shuo Yang Bao) ty-xyg-22 (Ningbo Tianyi) ... | Esophagogastric junction malignant tumor; Gastric lymph node metastatic malignant tumor |


## Evaluation Plan

- (1) The competition will use accuracy as the final evaluation criterion. In this task, accuracy is defined as follows: Accuracy = Number of correctly predicted combinations of (diagnosis + surgery + drug + doctor's orders) / Total number of (diagnosis + surgery + drug + doctor's orders) to be predicted.
- (2) Training data: 2700 records, Testing data: 337 records.
- (3) Submission of test set predictions in a file format with the following conventions:
  - a) File name: prediction.txt
  - b) Each line represents a record in the format: Discharge Diagnosis\tSurgery Name\tPreoperative Diagnosis\tPostoperative Diagnosis\tAdmission Diagnosis\tDrug Name\tDoctor's Orders\tStandard Terms \n. Note that when there are multiple standard terms, separate them with a semicolon, for example: Standard Term 1; Standard Term 2.
  - c) The order of records should match that of the test set.



