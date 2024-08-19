# CHIP 2022 AGAC


## Task Overview/Task Details

### Task Overview

In a massive collection of scientific literature, the mechanism of the "gene-disease" association is described through mutations, genes, and other series of molecular objects and their trigger words. Natural language processing provides the possibility for automatically mining this implicit knowledge entry and also offers a solution for the automated handling of health and medical information. This task includes three subtasks: 1. Trigger word entity recognition; 2. Semantic role labeling; 3. Extraction of "Gene, Regulation Type, Disease" triplets. All data is taken from the AGAC corpus.

### Task Details

#### Task One: Trigger Word Entity Recognition

Task One is traditional Named Entity Recognition, used to identify twelve classes of molecular objects related to "gene-disease" and their trigger word entities, including Var, MPA, Interaction, Pathway, CPA, Reg, PosReg, NegReg, Disease, Gene, Protein, and Enzyme.

#### Task Two: Semantic Role Labeling

Task Two is a Semantic Role Labeling task, where semantic roles include ThemeOf and CauseOf. This task captures semantic dependency relationships between entities to build the "gene-disease" association.

#### Task Three: "Gene, Regulation Type, Disease" Triplet Extraction

Task Three is a Triplet Extraction task focused on extracting relevant semantics for the regulatory types of the mechanism of the "gene-disease" association. It can utilize trigger words and their semantic roles obtained from Task One and Task Two to mine the underlying deep semantics. Here, regulatory types include four semantic descriptions of mutated genes: Loss of Function (LOF), Gain of Function (GOF), Regulation (REG), and Complex Changes in Function (COM). This task provides the results of "Gene, Regulation Type, Disease" triplets from 250 training texts.

#### Logical Relationships Between Subtasks

Participants can choose to participate in any of the subtasks, but Task One is based on Task Two, and Task Three can be executed independently or based on the results of Task One or Task Two.


## Data Description

### Data Sample

The data format for Task One and Task Two is JSON, including the following content:


```json
{ "target" : "http://pubannotation.org/docs/sourcedb/PubMed/sourceid/25805808", "sourcedb" "PubMed", "sourceid" : "25805808", "text" : "Loss-of-function de novo mutations play an important role in severe human neural tube defects.\nBACKGROUND: Neural tube defects (NTDs) are very common and severe birth defects that are caused by failure of neural tube closure and that have a complex aetiology. Anencephaly and spina bifida are severe NTDs that affect reproductive fitness and suggest a role for de novo mutations (DNMs) in their aetiology.\nMETHODS: We used whole-exome sequencing in 43 sporadic cases affected with myelomeningocele or anencephaly and their unaffected parents to identify DNMs in their exomes.\nRESULTS: We identified 42 coding DNMs in 25 cases, of which 6 were loss of function (LoF) showing a higher rate of LoF DNM in our cohort compared with control cohorts. Notably, we identified two protein-truncating DNMs in two independent cases in SHROOM3, previously associated with NTDs only in animal models. We have demonstrated a significant enrichment of LoF DNMs in this gene in NTDs compared with the gene specific DNM rate and to the DNM rate estimated from control cohorts. We also identified one nonsense DNM in PAX3 and two potentially causative missense DNMs in GRHL3 and PTPRS.\nCONCLUSIONS: Our study demonstrates an important role of LoF DNMs in the development of NTDs and strongly implicates SHROOM3 in its aetiology.", "project": "AGAC2_PubMed_2", "denotations" : [ { "id": "T8", "span": { "begin": 771, "end": 778 }, "obj": "Protein" }, { "id": "T7", "span": { "begin": 779, "end": 789 }, "obj": "NegReg" }, { "id": "T6", "span": { "begin": 790, "end": 794 }, "obj": "Var" }, { "id": "T9", "span": { "begin": 823, "end": 830 }, "obj": "Gene" }, { "id": "T10", "span": { "begin": 936, "end": 939 }, "obj": "NegReg" }, { "id": "T11", "span": { "begin": 940, "end": 944 }, "obj": "Var" }, { "id": "T12", "span": { "begin": 961, "end": 965 }, "obj": "Disease" }, { "id": "T3", "span": { "begin": 1224, "end": 1227 }, "obj": "NegReg" }, { "id": "T1", "span": { "begin": 1228, "end": 1232 }, "obj": "Var" }, { "id": "T2", "span": { "begin": 1255, "end": 1259 }, "obj": "Disease" }, { "id": "T5", "span": { "begin": 1284, "end": 1291 }, "obj": "Gene" } ], "relations" : [ { "id": "R1", "pred": "CauseOf", "subj": "T1", "obj": "T3" }, { "id": "R10", "pred": "ThemeOf", "subj": "T12", "obj": "T10" }, { "id": "R11", "pred": "ThemeOf", "subj": "T5", "obj": "T1" }, { "id": "R2", "pred": "ThemeOf", "subj": "T2", "obj": "T3" }, { "id": "R5", "pred": "CauseOf", "subj": "T6", "obj": "T7" }, { "id": "R6", "pred": "ThemeOf", "subj": "T8", "obj": "T7" }, { "id": "R7", "pred": "ThemeOf", "subj": "T9", "obj": "T6" }, { "id": "R8", "pred": "ThemeOf", "subj": "T9", "obj": "T11" }, { "id": "R9", "pred": "CauseOf", "subj": "T11", "obj": "T10" } ]}
```


#### Data Format Description:

The data format is in JSON and includes the following content:

- "target": Address of the annotated text

- "sourcedb": Source of the text, all texts in AGAC are from PubMed

- "sourceid": PMID of the text

- "text": Original abstract text

- "denotations": Annotations for trigger words corresponding to Task One, including "id", "span" indicating the position information of the entity in the text, and "obj" representing the labeled tag for the entity

- "relations": Semantic roles between trigger words corresponding to Task Two, including "id", "pred" indicating the semantic role, and "subj" and "obj" representing the "id" of the trigger words from Task One, with the association direction from "subj" to "obj"

#### Explanation of "Gene, Regulation Type, Disease" Triplet Data for Task Three:



| PMID     | Gene  | Regulation Type | Disease                        |
|----------|-------|------------------|--------------------------------|
| 19338054 | MC1R  | LOF              | melanoma                       |
| 18594199 |       |                  |                                |
| 20399956 | Shp2  | GOF              | juvenile myelomonocytic leukemia|
|          | Shp2  | LOF              | LEOPARD syndrome                |


#### Data Format Description:

Task Three data consists of four columns: PMID, Gene, Regulation Type, and Disease. Each text may not extract any triplet relationships, or it may extract multiple triplet relationships.



## Training and Testing Data

### Task One:

Training Data: 250 PubMed articles
Testing Data: 2000 PubMed articles

### Task Two:

Training Data: 250 PubMed articles
Testing Data: 2000 PubMed articles

### Task Three:

Training Data: 250 PubMed articles with extracted triplet relationships
Testing Data: 2000 PubMed articles


## Task Object

The definition of task objects is derived from the Active Gene Annotation Corpus (AGAC), which is primarily used to explore the mechanism of "gene-disease" associations caused by mutations. The AGAC corpus includes four classes of molecular objects, eight classes of trigger word entities, two semantic roles, and four types of functional changes used to describe the mechanism of "gene-disease" associations. Note: In AGAC, only sentences that involve specific mutations and biological functions or diseases are annotated.

### Recognition Objects for Task One:

- Molecular Entities
  - Disease
  - Gene
  - Protein
  - Enzyme
- Trigger Word Entities
  - Variation (Var): Includes mutations in DNA, RNA, proteins, and changes in molecular structures. Examples of annotated entities include "mutations on the Arg248 and Arg282," "mutant R282W," "missense mutations."
  - Molecular Physiological Activity (MPA): Molecular-level activities including molecular activity, gene expression, and molecular physiological activity. Examples of annotated entities include "phosphorylation," "transcription," "histone methylation," "bioactivation of cyclophosphamide."
  - Interaction: Connections between molecules, or between molecules and cells. Examples of annotated entities include "bind," "interaction."
  - Pathway: Various pathways such as "Bmp pathway," "PI3K pathway."
  - Cell Physiological Activity (CPA): Activities at or above the cellular level, including cell reactivity and development and growth of cells or organs. Examples of annotated entities include "T helper cell responses," "renal development."
  - Regulation (Reg): Neutral hint words or phrases indicating no loss or gain, such as "resulted in," "regulated."
  - Positive Regulation (PosReg): Indicating clues or phrases for gain of function, such as "facilitates," "enhanced," "increased."
  - Negative Regulation (NegReg): Indicating clues or phrases for loss of function, such as "suppressed," "decreased," "inhibited."

### Annotation Objects for Task Two:

- Semantic Roles
  - ThemeOf: Points from the main entity (Theme) to the current entity
  - CauseOf: Points from the current entity to the causing entity (Cause)

### Extraction Objects for Task Three:

- Regulation Types

LOF and GOF indicate loss or gain of function, respectively.
REG represents a general regulatory relationship.
COM indicates a more complex change in function between genes and diseases, making it difficult to determine whether it is LOF or GOF.
During prediction, extract triplets "gene; regulation type; disease" from the text, for example: "SHROOM3; LOF; Neural tube defects," or include PMID information: "25805808; SHROOM3; LOF; Neural tube defects."



## Evaluation Metrics

Precision, Recall, F-score



