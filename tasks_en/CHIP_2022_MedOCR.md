# CHIP 2022 MedOCR

## Task Background

The medical records currently used in hospitals are primarily paper-based, containing information such as patient details, diagnosis information, medication details, and cost information. In the medical and insurance industries, this information holds significant commercial and research value, and its extraction poses challenges, often relying heavily on manual data entry.
With the gradual development and adoption of artificial intelligence technologies like OCR and NLP in daily production and life, the application of OCR and NLP technologies can effectively enhance work efficiency and reduce the training costs of business personnel compared to traditional manual data entry methods. The electronic and structured conversion of information from these paper materials using OCR and NLP technologies is becoming a hot topic in the industry.
The dataset for this task includes four types of medical records: discharge summaries, outpatient invoices, prescription invoices, and inpatient invoices. The main focus is on extracting data from images in real-life scenarios and generating electronically structured data.


## Field Extraction Description

Field attribute names are free from business logic and use the original field attribute names found in the materials. Fields not listed below will not be included in the final result evaluation.

- (1) Discharge Summary (8 attributes in total)

Patient Information (2 attributes): Gender, Age

Hospital Information (6 attributes): Hospital Name, Organizational Code, Medical Institution Type, Admission Date, Discharge Date, Length of Stay

- (2) Outpatient Invoice (34 attributes in total)

Patient Information Field (1 attribute): Gender

Invoice Information Fields (7 attributes): Invoice Code, Invoice Number, Validation Code, Invoice Date, Payee, Payee, Reviewer

Medical Insurance Information Fields (2 attributes): Medical Institution Type, Insurance Type

Item Information Fields (14 attributes): Examination Fee, Inspection Fee, Laboratory Fee, Treatment Fee, Surgery Fee, Health Material Fee, Western Medicine Fee, Traditional Chinese Medicine Fee, Chinese Patent Medicine Fee, General Medical Fee, Bed Fee, Nursing Fee, Registration Fee, Other Charges

Payment Information Fields (10 attributes): Total Amount (in words), (in figures), Medical Insurance Fund Payment, Overall Payment, Individual Cash Payment, Individual Account Payment, Individual Self-payment, Other Payments, Self-payment One, Self-payment Two

- (3) Prescription Invoice (8 attributes in total)

Invoice Information Fields (6 attributes): Invoice Code, Invoice Number, Validation Code, Invoice Date, Payee, Reviewer

Payment Information Fields (2 attributes): Total Amount (in words), (in figures)

- (4) Inpatient Invoice (37 attributes in total)

Patient Information Fields (4 attributes): Gender, Admission Date, Discharge Date, Length of Stay

Invoice Information Fields (7 attributes): Invoice Code, Invoice Number, Validation Code, Invoice Date, Payee, Payee, Reviewer

Medical Insurance Information Fields (2 attributes): Medical Institution Type, Insurance Type

Item Information Fields (14 attributes): Examination Fee, Inspection Fee, Laboratory Fee, Treatment Fee, Surgery Fee, Health Material Fee, Western Medicine Fee, Traditional Chinese Medicine Fee, Chinese Patent Medicine Fee, General Medical Fee, Bed Fee, Nursing Fee, Registration Fee, Other Charges

Payment Information Fields (10 attributes): Total Amount (in words), (in figures), Medical Insurance Fund Payment, Overall Payment, Individual Cash Payment, Individual Account Payment, Individual Self-payment, Other Payments, Self-payment One, Self-payment Two


## Evaluation Criteria

**Accuracy**

Accuracy = Number of Correct Predictions / (Number of Correct Predictions + Number of Incorrect Predictions) 

Note:
If both the predicted and correct values are "none," it is considered "not calculated."
If the predicted value exactly matches the correct value, it is considered "correct prediction"; otherwise, it is considered "incorrect prediction."

## Dataset

### Translation into English and Markdown Table Code:

| Dataset           | Description                                                                                                             |
|-------------------|-------------------------------------------------------------------------------------------------------------------------|
| Training Set      | Real data images and annotations (total of 1000 images) across all material types: Prescription Invoices: 200 images; Outpatient Invoices: 200 images; Inpatient Invoices: 200 images; Discharge Summaries: 400 images |
| Evaluation Set A  | Real data images and annotations (total of 200 images) across all material types                                        |
| Evaluation Set B  | Real data images and annotations (total of 500 images), with a submission time limit of 48 hours for Set B              |









