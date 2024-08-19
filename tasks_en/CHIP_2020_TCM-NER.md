# CHIP 2020 TCM-NER


## Task Description

Under the catalysis of the epidemic, artificial intelligence is continuously assisting in the accelerated development of the inheritance and innovation of traditional Chinese medicine, with the excavation and accumulation of the knowledge system of traditional Chinese medicine being a fundamental task. By mining the instructions of Chinese herbal medicine to construct a knowledge graph for the rational use of traditional Chinese medicine, a solid foundation will be laid for the standardized diagnosis and treatment of traditional Chinese medicine. The challenge aims to extract key information from the instructions of traditional Chinese medicine products to achieve the goal of building a knowledge base for traditional Chinese medicine products.

## Task Details

This annotation task's data source comes from the instructions of traditional Chinese medicine products, which includes 1997 deduplicated drug instructions. Among them, 1200 are used for training data, 400 for preliminary test data, and the remaining 397 for the final test data. The final test data is not publicly available, not downloadable, and not visible. Participants need to submit through the mirror method on the Tianchi platform. Thirteen entity classes have been defined, with specific category definitions as follows:



## Entity Definitions:

- Drug (DRUG): Traditional Chinese medicine names, substances used under the guidance of traditional Chinese medicine theory for prevention, treatment, diagnosis of diseases, and rehabilitation and health care. Examples: Liuwei Dihuang Wan, Xiaoyao San

- Drug Ingredient (DRUG_INGREDIENT): The composition of traditional Chinese medicine, referring to all pharmacologically active ingredients closely related to the clinical application purposes of the traditional Chinese medicine compound. Examples: Angelica, Ginseng, Goji Berry

- Disease (DISEASE): Names of diseases that refer to abnormal life processes occurring in the body due to disturbances in self-regulation under certain damaging effects of various causes, affecting some or all organs of an organism. Examples: Hypertension, Angina, Diabetes

- Symptom (SYMPTOM): Subjective abnormal sensations or certain objective pathological changes caused by a series of abnormal functional, metabolic, and morphological changes in the body during the disease process. Examples: Dizziness, Palpitations, Lower abdominal distension and pain

- Syndrome (SYNDROME): A specific term in traditional Chinese medicine that refers to a collection of interrelated symptoms obtained through observation, listening, questioning, and pulse-taking during the disease process, representing the overall response status of the body at a holistic level and its movements and changes. Examples: Blood Stasis, Qi Stagnation, Deficiency of Qi and Blood, Deficiency of Qi and Blood

- Disease Group (DISEASE_GROUP): Concept encompassing disease names related to specific human tissue sites, not specific medical diseases. Examples: Kidney Disease, Liver Disease, Lung Disease

- Food (FOOD): Substances that can meet the normal physiological and biochemical energy needs of the body while prolonging normal life. Examples: Apple, Tea, Black Fungus, Radish

- Food Group (FOOD_GROUP): In traditional Chinese diet therapy, foods are classified into cold, hot, warm, and cool properties, and food groups are terms for foods with common attributes according to traditional Chinese medicine taboos. Examples: Greasy Foods, Spicy Foods, Cool-natured Foods

- Person Group (PERSON_GROUP): Specific groups related to the applicability and contraindications of traditional Chinese medicine. Examples: Pregnant Women, Women During Menstruation, Children, Adolescent Girls

- Drug Group (DRUG_GROUP): Concept referring to a group of drugs with common attributes, not specific drug names. Examples: Cough Medicine, Antipyretic Medicine

- Drug Dosage (DRUG_DOSAGE): The form drugs must be prepared in before clinical use for medical and preventive applications. Examples: Concentrated Pills, Honey Pills, Sugar-coated Tablets

- Drug Taste (DRUG_TASTE): The nature and aroma of drugs. Examples: Sweet, Sour, Bitter, Astringent, Cool

- Traditional Chinese Medicine Efficacy (DRUG_EFFICACY): General term referring to the main therapeutic functions and effects of drugs. Examples: Nourish Yin and Tonify the Kidneys, Eliminate Stasis and Generate New Tissue, Activate Blood and Resolve Stasis


## Data Description

Based on the brat (http://brat.nlplab.org/) open-source tool for annotation. Training data consists of .txt files for the original documents and .ann files for the annotation information (if visualization of annotated files is required in the brat tool, see the attached conf file); test data provides txt text, similar to training data, and participants need to output corresponding ann text for each txt text.

Each line includes: entity ID number (prefixed with T), entity category, start position, end position, and entity content. The "entity ID number" and "entity category," "end position," and "entity content" are separated by tabs, while "entity category," "start position," "end position" are separated by spaces. Follow the default annotation format of brat.

## Evaluation Metrics:

This challenge is a standard NER (Named Entity Recognition) task, with Micro Strict F1 as the final measurement standard.


