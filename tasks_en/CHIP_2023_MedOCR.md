# CHIP 2023 MedOCR


## Task Background

In the pharmaceutical distribution industry, a large number of paper documents are accumulated during business operations, such as drug registration certificates, drug GMP certificates, drug production licenses, drug instructions, etc. Among them, the drug instructions are statutory documents that contain important information about the drugs, serving as legal guidelines for drug selection and possessing high value.
The update frequency of drug instructions is often higher than common sources of clinical guidelines, medical textbooks, etc., and they are more difficult to extract. Although drug instructions from different manufacturers contain similar content, there are significant differences in formatting, and they contain both structured and unstructured information. Extracting relationships between drugs and other entities from unstructured text to build a medical knowledge graph can better serve downstream tasks such as prescription review, assisting in diagnosis and treatment, and patient health education.

## Task Details

According to the regulations of the Drug Administration, drug instructions must specify the drug name, ingredients, indications, dosage and administration, adverse reactions, and other content. The goal of this task is to use OCR recognition on scanned copies of drug instructions to extract specified paragraphs, generating structured data. Additionally, it involves mining core entities and relationships from the unstructured text of designated sections.


### Entity Types

| Entity Name         | Definition                                                                                                                                                                                          | Example           |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| Drug                | Substances used for the prevention, treatment, and diagnosis of diseases in humans, purposefully regulating human physiological functions with indications, functions, usage, and dosage specified, including Chinese medicine, chemical drugs, and biological products | Aspirin           |
| Disease             | Disturbances in the life activities caused by the disruption of homeostasis in the body under certain pathogenic effects                                                                                | Neonatal jaundice |
| Clinical Observation| Patient-related conditions seen in clinical observations, including symptoms and signs                                                                                                               | Fever             |


### Relation Types

| Relationship Type | Relationship Subtype | Definition                                                                                                                                                                                                      |
|-------------------|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Drug-Disease       | Indication           | Indicates the drug is suitable for certain diseases or conditions.                                                                                                                                              |
| Drug-Disease       | Contraindication     | Indicates the drug is unsuitable or prohibited for use in certain diseases, and serious adverse effects may result from use.                                                                                   |
| Drug-Disease       | Adverse Reaction     | Refers to diseases unrelated to the therapeutic purpose that occur when drugs are used for prevention, diagnosis, or treatment under normal conditions.                                                          |
| Drug-Clinical Finding | Indication         | Indicates the drug is suitable for certain symptoms or signs.                                                                                                                                                   |
| Drug-Clinical Finding | Contraindication   | Indicates the drug is unsuitable or prohibited for use in certain symptoms or signs, and serious adverse effects may result from use.                                                                           |
| Drug-Clinical Finding | Adverse Reaction   | Refers to harmful reactions that occur when drugs are used for prevention, diagnosis, or treatment under normal conditions but are unrelated to the treatment purpose.                                         |
| Drug-Drug           | Drug Interaction     | Refers to the combined effects that occur when other drugs are taken simultaneously or within a certain period, which can enhance the efficacy or reduce side effects, or weaken the efficacy or cause unexpected toxic side effects. |
| Drug-Drug           | Additive Effect      | Refers to the effect produced when two drugs are used together that is equal to or close to the sum of the effects produced when used separately. When two drugs act on the same site or receptor and have the same effect, they often exhibit an additive effect.  |
| Drug-Drug           | Synergistic Effect   | Refers to the enhanced effect of each drug when used in combination with other drugs.                                                                                                                             |
| Drug-Drug           | Antagonistic Effect  | Refers to the weakening or disappearance of the effect produced when other drugs are used in combination, and in most cases, they should not be used together.                                               |
| Drug-Drug           | Incompatibility      | Refers to the phenomenon where drugs have a physical or chemical interaction outside the body, affecting the efficacy of the drugs or causing toxic reactions.                                                     |


## Data Description
This annotation data is all sourced from drug instructions.

### Structured Field Description:

Field attribute names are not mixed with business logic and use the original field attribute names from the instructions. Fields not included in the following field attribute names are not involved in the final result evaluation.

Drug instruction fields (total of 17): Generic name, brand name, specifications, ingredients, indications (chemical drugs) / functions and indications (Chinese patent medicines), characteristics, dosage and administration, adverse reactions, contraindications, precautions, drug interactions, drug use in pregnant and lactating women, pediatric use, geriatric use, pharmacology and toxicology, pharmacokinetics, storage.

### Input/Output:

- Input: Images of drug instructions.

- Output: Recognized fields and entity relationships that meet the specified types as triples, in JSON format, including the following contents:

"vertex": Source entity

"vertexName": Entity name

"edgeType": Relationship subtype

"target": Target entity

"targetName": Target entity name



## Evaluation Criteria

- Average Character Error Rate (average-CER): The average CER of all fields, where CER = edit distance / total number of characters. If both the predicted and correct values are "none," it is considered as "not included in the calculation."

- Macro-F1 score for triple extraction

- The final score is calculated as follows:
score=0.3×(1−average-CER)+0.7×Macro-F1


## Dataset Description

| Dataset                | Description                                                   |
|------------------------|---------------------------------------------------------------|
| Recognition Training Set | 400 real data images with annotations                        |
| Recognition Evaluation Set A | 200 real data images with annotations                    |
| Recognition Evaluation Set B | 400 real data images with annotations, submission time limited to 48 hours |

