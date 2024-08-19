# CHIP 2022 Text2DT


## Task Introduction

As the core of intelligent medical systems such as auxiliary diagnostic systems and medical education, the acquisition of diagnostic decision trees often relies on manual construction by medical experts, requiring a significant amount of domain knowledge and time. Therefore, exploring how to automatically extract diagnostic decision trees from sources of diagnostic decision knowledge (clinical practice guidelines, medical textbooks) is highly meaningful. Clinical diagnosis and treatment can be seen as a process of making judgments based on different conditions and then making different decisions. This clinical diagnosis and treatment process can be modeled as a clinical diagnostic decision tree, which consists of a tree-like structure composed of conditional nodes and decision nodes, where conditional nodes represent the conditional judgments to be made and decision nodes represent the diagnostic decisions to be made.

## Task Details

The goal of Text2DT is to extract diagnostic decision trees from given medical texts. A diagnostic decision tree represents a simplified decision-making process, where based on different outcomes of conditional judgments, the next conditional judgment or decision is made. Once a decision is made, the diagnostic process terminates. Therefore, we define the diagnostic decision tree as a binary tree composed of conditional nodes and decision nodes. This task requires the model to not only extract core entities and relationships from the text but also to link this information together to form a complete decision-making process.


## Data Description

The annotated data for this task is sourced entirely from annotations on publicly available clinical practice guidelines and medical textbooks.

- Training Data: 300 samples
- Validation Data: 100 samples
- Test Data: 100 samples

### Medical Text Example:
"A patient with subacute thyroiditis: Mild patients only need to use non-steroidal anti-inflammatory drugs, such as aspirin, ibuprofen, etc.; moderate and severe patients can be given prednisone orally at 20-40mg three times a day."

### Example Data


**Input (Medical Text):** Subacute thyroiditis patients: Mild patients only need to use non-steroidal anti-inflammatory drugs, such as aspirin, ibuprofen, etc.; moderate and severe patients can be given prednisone 20-40mg orally three times a day.

**Output** (Preorder sequence of a decision tree representing decision-making):

```json
[
        {'role':'c','triples':[['亚急性甲状腺患者','临床表现','轻型']],'logical_rel':'null'},

        {'role':'d','triples':[['亚急性甲状腺患者','治疗药物','非甾体抗炎药'],['亚急性甲状腺患者','治疗药物','阿司匹林'],['亚急性甲状腺患者','治疗药物','布洛芬']],'logical_rel':'or'},

        {'role':'c','triples':[['亚急性甲状腺患者','临床表现','中型'],['亚急性甲状腺患者','临床表现','重型']],'logical_rel':'or'},

        {'role': 'd', 'triples': [['亚急性甲状腺患者', '治疗药物', '泼尼松'], ['泼尼松', '用法用量', '每日20~40mg分3次口服']], 'logical_rel':
        'and'},

        {'role': '','triples':'','logical_rel':''}

]
```

## Evaluation Methods:

- F1 score of triple extraction.
- Accuracy of decision tree: The extracted decision tree is considered correct when this tree is completely consistent with the ground truth (tree structure, triples, logical relationships).
- F1 score of decision paths: We define a decision path as the path from the root node to a leaf node, representing the process of making a decision based on conditional judgments. The F1 score of decision paths serves as a more lenient evaluation metric compared to the accuracy of the decision tree. For example, as shown in Figure 2, this tree has a total of 2 decision paths.
- Edit Distance of Decision Trees: Similar to the edit distance of strings, the edit distance in diagnostic and treatment decision trees is the minimum number of tree editing operations required to transform one tree into another. Tree editing operations include inserting and deleting nodes, changing the roles of nodes, inserting or deleting triples, and modifying the logical relationships between triples. The edit distance can measure the similarity between two trees and serves as a more lenient evaluation metric compared to the accuracy of the decision tree. The edit distance between the following two trees is 5 (meaning to transform the first tree into the second tree, you would need to: 1. Add the triple (Patient, Clinical Presentation, Severe); 2. Add the logical relationship OR; 3. Change the logical relationship OR to AND; 4. Delete the triple (Patient, Treatment Drug, Ibuprofen); 5. Add the triple (Patient, Treatment Drug, Prednisone)).







