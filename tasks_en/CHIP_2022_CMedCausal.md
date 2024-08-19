# CHIP 2022 CMedCausal


## Task Background

Modern healthcare places a strong emphasis on interpretability, requiring doctors in diagnosis, treatment, and assessment to start from a patient-centered perspective, highlighting the causal relationships in healthcare. Therefore, there is a large amount of causal relationship explanations in medical question-and-answer and knowledge-based texts on the internet. These explanations not only help patients but also have tremendous value for medical search and diagnostic businesses. From these texts, causal relationships can be extracted to build a causal relationship explanation network, construct a medical causal knowledge graph, and enhance the logical and explanatory judgment capabilities of medical outcomes. Following the release of the "Medical Dialogue Clinical Discovery Positive and Negative Discrimination Task" at CHIP 2021, this year, Alibaba's Quark Medical team has released the "Medical Causal Relationship Extraction Task."

## Task Introduction

### Task Definition

Fine-grained annotation of causal relationships involves annotating medical concept segments on the basis of existing causal relationships and annotating the relationship roles between medical concept segments. Specifically, the fine-grained medical concept segments are divided into the following 3 types:

#### Causal Relationship:

A causal relationship refers to a situation where a certain cause directly leads to a specific result.

Example: Dysfunction of the gastrointestinal tract in the human body leads to a decrease in the patient's absorption ability.

Explanation: Dysfunction of the gastrointestinal tract is a direct cause of the decrease in absorption ability. The decrease in absorption ability is a direct result of gastrointestinal dysfunction.

#### Conditional Relationship:

A conditional relationship refers to specific conditions within medical concept segments used to modify specific causal relationships. Note: Conditions do not directly cause the occurrence of a particular result.

Example 1: Patients allergic to amoxicillin should not use it; taking amoxicillin can cause rash, drug fever, and asthma reactions, so a penicillin skin test must be done before use.

Explanation: In this case, being allergic to amoxicillin is a condition for amoxicillin leading to a rash.

Example 2: If already pregnant, experiencing lower abdominal pain or vaginal bleeding can be considered a sign of threatened miscarriage.

Explanation: Under the condition of pregnancy, lower abdominal pain or vaginal bleeding is generally caused by a threatened miscarriage. In other words, the modified causal relationship can only occur under specific conditions.

#### Hyponym-Hypernym Relationship:

The hyponym-hypernym relationship refers to the size relationship between concepts.
Example: Alzheimer's disease is a type of mental disorder that is quite common in daily life.
Explanation: In this case, Alzheimer's disease is a type of mental disorder, establishing a hyponym-hypernym relationship with mental disorders.


### Annotation Guidelines

- Entities should be annotated as comprehensively as possible to include useful information such as the severity and frequency of symptoms. Irrelevant information should not be included in the annotation scope. For example, in the phrase "Failure to treat promptly may cause pain locally," the annotation should include "may cause pain locally" rather than just "pain" to avoid information loss. If distinguishing disease characteristics requires referencing specific populations, those populations should also be annotated, as in "baby cough."

- Relationships between diseases and clinical presentations are classified as causal relationships for this annotation task. For example, in the statement "Cough is a common symptom of a cold," the relationship between "cold" and "cough" is considered causal.

- For long mentions where multiple entities are connected, annotations should follow the following rules: if each entity has independent significance, they should be annotated separately. For example, in the phrase "osteonecrosis of the femoral head caused by excessive drinking, steroid use, and fatigue," annotations should include ("excessive drinking," "osteonecrosis of the femoral head"), ("steroid use," "osteonecrosis of the femoral head"), and ("fatigue," "osteonecrosis of the femoral head") for three causal relationships. If the entities are non-continuous, they should be merged into a single long mention. For instance, in "consumption of cheese, chocolate, and cola leads to obesity," the annotation would be ("consumption of cheese, chocolate, and cola," "obesity") for one causal relationship.

- This task only annotates direct relationships and does not annotate derived relationships. For example, if "A leads to B, and B in turn leads to C," this task would only annotate the relationships (A, B) and (B, C), not (A, C). Similarly, for hyponym-hypernym or alias situations, only the most intuitive entities should be annotated. For example, in "A, also known as B, causes C," only annotate (A, C).

- This task is based on paragraph annotation, so relationships spanning across sentences will be annotated.

- Some descriptions may involve common knowledge and may not fit into the three relationship categories defined for this task.


### Annotation Example

```json
{
    "text": "在心率规整的情况下,脉搏的频率与心率是一样的,成年人的脉搏一般在60-100次之间,大部分在70-80次之间,怀孕后的女性由于生理性贫血的影响以及循环血量增加使心脏的负担加重,可能会使心率相对增快。",
    "relation_of_mention": [
      {
        "head": {
          "mention": "怀孕后的女性",
          "start_idx": 55,
          "end_idx": 61
        },
        "relation": 2,
        "tail": {
          "type": "relation",
          "head": {
            "mention": "生理性贫血",
            "start_idx": 63,
            "end_idx": 68
          },
          "relation": 1,
          "tail": {
            "mention": "心脏的负担加重",
            "start_idx": 80,
            "end_idx": 87
          }
        }
      },
      {
        "head": {
          "mention": "怀孕后的女性",
          "start_idx": 55,
          "end_idx": 61
        },
        "relation": 2,
        "tail": {
          "type": "relation",
          "head": {
            "mention": "循环血量增加",
            "start_idx": 73,
            "end_idx": 79
          },
          "relation": 1,
          "tail": {
            "mention": "心脏的负担加重",
            "start_idx": 80,
            "end_idx": 87
          }
        }
      },
      {
        "head": {
          "mention": "心脏的负担加重",
          "start_idx": 80,
          "end_idx": 87
        },
        "relation": 1,
        "tail": {
          "type": "mention",
          "mention": "心率相对增快",
          "start_idx": 92,
          "end_idx": 98
        }
      }
  ]
}
```

### Data Description

Provided in JSON format, including the following fields:

- text: Paragraph text

- relation_of_mention: List of relationship triplets, with each element being a relationship triplet consisting of 3 fields: "head", "relation", and "tail".
  - The "relation" field includes three types of relationships, represented by the numbers 1, 2, 3, corresponding to "causal", "conditional", and "hyponym-hypernym" relationships. Note that the relationships have a specific order: in causal relationships, "head" and "tail" respectively represent the cause and effect; in conditional relationships, "head" and "tail" represent the condition and the causal relationship being modified; in hyponym-hypernym relationships, "head" and "tail" represent the hypernym and hyponym terms.
  - The "head" includes "mention", "start_idx", and "end_idx" fields, representing the entity fragment, text start, and end indices. Indexing follows the left-closed, right-open convention.
  - The "tail" includes "type" and other fields. The "type" field is primarily used to differentiate conditional relationships from the other two types. When the "relation" is a causal or hyponym-hypernym relationship, the type is "mention", and the tail entity is also an entity, similar to the head entity, including "mention", "start_idx", and "end_idx" fields; when the "relation" is a conditional relationship, the type value is "relation", and the tail entity is the causal relationship modified by the head entity, following the definition of a causal relationship, including "head", "relation", and "tail" fields.


## Dataset

This evaluation provides a total of 2,000 dialogue corpora as the training set. The testing phase is divided into two stages, A and B lists, each providing 1,000 dialogues for testing. For the B list, submissions are limited to a 48-hour window.

## Evaluation Metrics

The evaluation for this assessment employs Macro-F1 as the evaluation metric.










