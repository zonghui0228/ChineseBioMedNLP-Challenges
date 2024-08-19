# CCKS 2021 Phe-Drug-Mol

## Task Description

Over the past three decades, Target-based Drug Discovery (TDD) has been the primary method for drug discovery. Due to the clear targets, using TDD makes it easy to design drug screening experiments, leading to numerous successful cases in the past. Developing drugs using the TDD method makes the time, process, and required resources for drug discovery predictable.

In recent years, with the rapid development of cell phenotype screening technologies such as induced pluripotent stem cells (iPS) technology, CRISPR-Cas technology, organoids, and imaging analysis technologies, Phenotypic Drug Discovery (PDD) has re-entered the spotlight. Researchers in drug discovery need to conduct a large number of biological experiments on various drugs to determine their therapeutic effects, a step that consumes a significant amount of time.

Machine learning is a powerful branch of AI that accelerates research through complex data-driven solutions. Over the past decade, AI methodologies and machine learning algorithms have been successfully applied at various stages of drug discovery and have gradually integrated into the drug discovery strategies of large pharmaceutical companies. In the era of big data and artificial intelligence, we can collect vast amounts of clinical and experimental data and use AI algorithms to predict the targeted effects of drugs and genes, as well as the therapeutic effects of drugs on phenotypes.

One approach to addressing this issue is through knowledge graphs. By constructing a multi-level knowledge graph of phenotypes-drugs-molecules and using large-scale graph algorithms and knowledge inference to predict relationships between diseases, symptoms, drugs, genes, side effects, and more. The multi-level knowledge graph of phenotypes-drugs-molecules is built based on relationships between phenotypes (diseases, symptoms), drugs, genes, and other entities, containing a wealth of entity and relationship data to support research on pathogenesis and pharmacological mechanisms. Understanding these issues is of significant practical significance and academic value for further elucidating the molecular mechanisms of diseases and exploring potential drug treatment mechanisms.

This task focuses on relationship prediction based on the multi-level knowledge graph of phenotypes-drugs-molecules, such as the targeted effects of drugs on genes/proteins, the therapeutic effects of drugs on phenotypes, interactions between proteins, and more. Evaluation is based on the schema of the knowledge graph and the entities and relationships within it, predicting the relationships between two new entities. The evaluation does not restrict the models, algorithms, or technologies used by participating teams. Various graph algorithm models and pre-training methods can be utilized for relationship prediction on the graph, collectively advancing the development of knowledge graph technology.

## Input/Output

### Input:

schema.json: Schema of the knowledge graph, defining entity types (Entity) and relationships between entities (Relationship).

entities.json: List of entities, including drugs, genes, phenotypes (diseases and symptoms), gene pathways, and other entities.

relationships.json: List of relationships between entities, such as drug-gene, drug-disease, drug-symptom, disease-symptom, disease-gene, symptom-gene, protein-protein relationships, and more.

link_prediction.json: Pairs of head and tail entities with relationships to be evaluated.

### Output:

result.txt: Predicted top 10 head or tail missing entity queues for each missing entity relationship pair (ordered by likelihood from high to low). Participants should remove entity data with existing links in the training set from the queues to prevent occupying and wasting queue positions.

### Input Example:

schema.json:

```json
{
    "entity_type": ["disease", "drug", "gene/protein", ……],
    "relationships": [["disease", "associated_with", "symptom"], ["disease", "disease_mapped_to_gene", "gene/protein"], ["drug", "treats", "disease"], ……],
}
```

entities.json：

```json
{   
    "disease": ["C0008626", "C3805375", "C1561850", "C0733682", ...],
"gene/protein": ["SEPT4", "MARCH2", "SEPT8", …],
…
}
```

relaionships.json
```json
{
    "relationships": [["DB00855","treats","C0020649"], ["DB00855","treats","C0037274"],
      …
]
}
```

link_prediction.json
```json
{
    "relationships": [["DB01623","treats","?"], ["PSMC3","interacts_with","?"],
      …
]
}
```

### Output Example:

link_prediction.json:

```json
{
"results": 
[
[A1, B1, C1, D1, …],
[A2, B2, C2, D2, …],
……
]
}
```


## Description of Knowledge Graph

The knowledge graph in this task is built based on phenotypes (diseases, symptoms), drugs, genes, and their relationships, containing a vast amount of entity and relationship data. It can provide certain support for the study of pathogenesis and pharmacological mechanisms. Predicting the relationships between diseases, symptoms, drugs, genes, side effects, etc., is an important issue in medical research. These problems have significant practical significance and academic value for further understanding the molecular mechanisms of diseases and exploring potential drug treatment mechanisms.

The knowledge graph in this task contains the following seven types of relationships:

The "associated_with" relationship can be used to represent the connection between diseases and symptoms. By exploring potential relationships between diseases and symptoms through existing relationships, it helps improve our understanding of disease symptoms.

"disease_mapped_to_gene" represents the relationship between diseases and genes. Analyzing the relationships between a large number of associated diseases and genes can reveal potential connections between diseases and genes, which is of great importance for disease prevention and treatment.

The "treats" relationship is the correspondence between drugs and diseases. As an important method for treating diseases, effective drugs have always been a continuous pursuit. Many potential effects of drugs have not been discovered, and analyzing the data we provide will help address this issue.

The "targets" relationship represents the relationship between drugs and genes. Studying the relationship between drugs and genes aims to more accurately find treatment strategies. Developing drugs that target specific genes can significantly help in treating diseases.

"interacts_with" is the relationship between genes. In many cases, diseases are not only related to one gene; usually, multiple genes collectively affect a certain disease. Therefore, exploring the relationships between genes helps discover more pathogenic genes, thus providing more comprehensive evidence for treating diseases.

"annotates" and "pathway_has_gene_element" respectively represent the relationships between gene pathways, GO ontology, and genes. Pathway enrichment analysis and GO analysis are two important gene enrichment methods that can find genes with common characteristics, thereby further exploring the information represented by these genes.




