# CHIP 2018 CNER-AE

The purpose of structuring medical imaging examination results is to extract and display important or target fields from lengthy medical descriptions. The goal of this structuring is to extract common fields related to "tumor-related diseases" from the text descriptions of medical imaging examination results.

The method of structuring medical imaging examination results involves identifying specific entities based on important or target fields, assigning certain relationships and logical judgments to each entity. When the text contains entities that meet the specified criteria and the relationships between these entities satisfy the set logical conditions, the results of the target fields are output.

## What is medical imaging?

Medical imaging is a medical discipline that uses medical imaging techniques to diagnose diseases in the human body and to perform minimally invasive diagnostic and therapeutic procedures on human diseases under the guidance of medical imaging technology. It is an important component of clinical medicine.


## Common methods in medical imaging

Common methods in medical imaging include X-rays, CT scans, MRI scans, and ultrasound (sonography).

## Presentation of medical imaging examination results
There are two main ways to present medical imaging examination results: 1. Image presentation; 2. Text presentation. In clinical practice, apart from radiologists specialized in imaging, the vast majority of doctors rely on the textual information in medical imaging examination results for their clinical assessments.

## What is a field?

A field generally refers to a target field, which includes the field name and the field result/value range. It is the specific name we want to extract from a piece of text description. (The field name is typically enclosed in a red box, while the field result is enclosed in a green box.)


## What is structuring?

Structuring is a method of extracting fields and making logical judgments. It involves finding specified entities and their logical relationships within a piece of text to derive certain results.



## Detailed explanation of the structuring of medical imaging examination results:

The structuring and field setting in this case are both conducted within the textual descriptions of medical imaging examination results.


## Diseases:

Lung cancer, breast cancer

## Imaging examinations:

CT, MRI

## Fields include:

- Primary tumor location: Normal tissues and organs' normal cells, under the long-term effects of various internal and external carcinogens, gradually transform into malignant tumor cells, forming a mass of cancer cells. The normal tissue or organ where this occurs is considered the primary tumor location.

- Lesion size: Refers to the size of abnormalities detected by imaging studies that differ from normal tissue, including benign and malignant lesions.

- Metastatic sites: Malignant tumor cells break away from the primary site and travel through lymphatic channels, blood vessels, or body cavities to other locations, where they continue to grow and form tumors of the same type as the primary tumor. These other sites are known as metastatic sites.


## Principles of structuring:

- Primary tumor location: In the conclusion of imaging examinations, doctors will directly provide a diagnostic conclusion. The first anatomical site mentioned in the diagnostic conclusion that is related to malignant tumor descriptions is considered the primary tumor location. Generally, there is only one primary tumor location.

- Lesion size: The sizes of individual lesions will be described in imaging findings. The results are output based on the sizes mentioned in the text, excluding duplicate entries.

- Metastatic sites: In the conclusion of imaging examinations, there will be explicit descriptions of metastases, often involving multiple sites. Metastatic sites are output according to the text, removing duplicates.

## Structuring rules explanation:

- Primary tumor location: In the examination conclusion, if an anatomical site is mentioned along with malignant tumor descriptors (such as malignant tumor, cancer, MT, CA) and there is no relation to metastasis criteria, that anatomical site is considered the primary tumor location. The original value is output, with only the first value being output. For example, in "malignant tumor in the upper lobe of the lung," "upper lobe of the lung" is the primary tumor location.

- Lesion size: The size description of imaging lesions mentioned in the examination findings (such as high-density shadow, low-density shadow, enhanced lesion) along with dimensions constitutes the lesion size. The original values are output, and all values are output without duplicates. For instance, in "a high-density shadow measuring 543cm seen in the liver," 543cm represents the lesion size.

- Metastatic sites: In the examination conclusion, if anatomical structures are mentioned along with indications of metastasis (metastasis, consideration of metastasis, highly suspected metastasis, metastatic focus, metastatic carcinoma, etc.), those anatomical structures are considered metastatic sites. The original values are output, and all values are output without duplicates. For example, in "metastases to the liver and kidneys," "liver and kidneys" are the metastatic sites.












