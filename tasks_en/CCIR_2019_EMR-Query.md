# CCIR 2019 EMR-Query


## Competition Task Description

In recent years, there has been significant progress in research on factual question answering based on knowledge graphs. However, for data query-based questions involving logical relationships and operations, there is currently no effective solution. The latter has wide applications and commercial value in professional fields. Electronic medical records are the main medium for recording patient information, and querying and analyzing electronic medical records have extensive uses in healthcare management and clinical research. In collaboration with AI healthcare companies, we are launching an evaluation of data query-based question answering based on electronic medical records, aiming to utilize next-generation AI technologies to perform queries, simple analysis, and reasoning on electronic medical records.


**Input:**

Query sentences described in natural language

**Output:**

 Query answers (two types: numeric or resource identifiers in the knowledge graph)


### Example:

#### Example 1:

**Input:** How many patients are there in total?


**Output:** 304


#### Example 2:

**Input:** Which patients underwent both phosphorus and creatine kinase tests simultaneously?

**Output:** peg-r:1, peg-r:29
