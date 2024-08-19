# CCKS 2020 Covid19

## Evaluation Background
With the rapid development of internet-related technologies, people are gradually transitioning from the information age to the intelligent age. Knowledge graphs, as important carriers that hold massive underlying knowledge and support upper-layer intelligent applications, play an extremely crucial role in the intelligent age. However, due to the significant differences between unstructured text and structured knowledge, challenges still exist in automatically constructing knowledge graphs and utilizing them to support upper-layer applications. Therefore, it is necessary to conduct research on the construction of knowledge graphs and their core applications, such as natural language question answering based on knowledge graphs.

Knowledge graphs can be divided into open domain and specific domain categories. Relatively speaking, the characteristic of open domain knowledge graphs is "broad but shallow," covering a wide range of entities but potentially lacking in-depth or uncommon knowledge in some areas. On the other hand, specific domain knowledge graphs are "specific and deep," covering only entity information in specific domains but including terms, concepts, and corresponding knowledge typically used by professionals in that particular field. With the development of knowledge sharing projects like LOD and OpenKG, merging or linking multiple knowledge bases from open and specific domains to form a comprehensive and in-depth "super" knowledge graph is gradually becoming possible.

In 2020, during the outbreak of the novel coronavirus pandemic, under the overall organization and coordination of OpenKG, some relevant companies and academic institutions used automated technologies to build high-quality knowledge graphs related to the novel coronavirus, including resources like the Coronavirus Encyclopedia, Health, and Prevention (http://openkg.cn/group/coronavirus). In this context, four evaluation subtasks were proposed focusing on the key technologies and core applications of knowledge graph construction. Typically, after entity recognition, assigning pre-defined types to each entity is necessary when building a knowledge graph. This leads to the first task we propose, "Entity Type Inference." Human-defined entity types have limited coverage and are not easily updated, and when dealing with new domains, the entity category system may need to be redefined. Dynamically acquiring entity concept categories in the network and automatically identifying hierarchical relationships between categories can not only address the shortcomings of manual definitions but also make the knowledge graph more comprehensive, aiding upper-layer applications. This leads to the second task we propose, "Prediction of Concept Hierarchical Relationships." To connect various entities in a knowledge graph, it is essential to determine which entities are related and which entities can be linked through specific relationships. This is the third task we propose, "Link Prediction." Finally, after completing the construction of the knowledge graph, querying it using natural language can greatly facilitate users in obtaining desired knowledge. Additionally, applications like smart speakers require allowing users to interact with knowledge graphs using natural language. This leads to the fourth task we propose, "Natural Language Question Answering for Knowledge Graphs."

The following will provide detailed introductions to the four tasks in this evaluation.

## Task Description

### 2.1 Subtask One: COVID-19 Encyclopedia Knowledge Graph Entity Type Inference

Type information holds significant value in knowledge bases, and research on entity type inference has always been a hot topic in the field. However, a large amount of type information is presented in the form of unstructured text on web pages, making text processing challenging. Ensuring high accuracy and coverage of extraction results remains a significant challenge. Several solutions have emerged in recent years for general entity type inference, including using statistical machine learning methods and leveraging external knowledge (links to other data sources or text information).

This evaluation task focuses on entity type inference (Entity Type Inference) in the construction of the COVID-19 Encyclopedia knowledge graph. The evaluation starts from entity encyclopedias (including Baidu Encyclopedia, Interactive Encyclopedia, Wikipedia, Medical Encyclopedia) and infers the types of relevant entities from the given data. The evaluation itself does not restrict the models, algorithms, and technologies that participating teams can use. It is hoped that participating teams will showcase their intelligence by building various types of systems, including unsupervised, weakly supervised, distantly supervised, semi-supervised, etc., to achieve entity type inference in knowledge graphs, collectively advancing the technology of knowledge graphs.

#### 2.1.1 Input and Output Specifications

**Input**

entity.txt: Contains all entities for which type prediction is needed, including relevant entities and noise entities.

entity_pages_1.xml, entity_pages_2.xml, entity_pages_3.xml, entity_pages_4.xml: Entity page content from Baidu Encyclopedia, Interactive Encyclopedia, Chinese Wikipedia, and Medical Encyclopedia, respectively. Ensure that any entity in entity.txt is covered by at least one page file. The entity page files contain information such as names, labels, and descriptions that may be used for type inference.

type.txt: Contains 7 target types, namely Virus, Bacteria, Disease, Medication, Medical Specialty, Examination Subject, Symptoms.

**Output**

entity_type.txt: Contains the entities and their predicted entity types, with each line representing an "entity\ttype" pair. Ensure that entities not belonging to the given 7 types are not included.



#### 2.1.2 Evaluation Metrics

This task utilizes precision (P), recall (R), and F1 score (F1-measure, F1) to evaluate the effectiveness of the entity type inference.


#### 2.1.3 Dataset

This task involves a total of around 175,000 entity pages. The task itself does not restrict the type of methods and can include unsupervised, semi-supervised, and supervised methods. Therefore, no specific training dataset is provided for the task. Participants are free to annotate training data as needed.

The test set is annotated by the organizers through automated entity type inference and manual verification. Participants are not allowed to perform any manual annotations on the test set.


### 2.2 Subtask Two: Prediction of Superordinate and Subordinate Relationships in the COVID-19 Concept Graph

In today's era of information technology, the categories of entities on the internet are diverse, with finer granularity and hierarchical structures. As opposed to traditional named entities with limited categories, attention has shifted towards open-domain entity mining.

The COVID-19 concept graph is an automatic construction of a conceptual schema knowledge graph. This graph utilizes automatic mining techniques to collect a large number of fine-grained superordinate concept terms from web text. The is-a hierarchical structure of this concept graph is automatically constructed and includes detailed superordinate and subordinate hierarchical structures.

Traditional knowledge graphs have very limited definitions of entity concept categories. For instance, ACE-2007 categorizes entities into 7 major classes and 45 subclasses, while Yosef (2013) divides entities into 505 classes. The advantage of manually defining entity categories is that it allows the entity recognition process to be treated as a classification problem, which can then be addressed using traditional pattern classification methods. However, predefining categories also has its inevitable drawbacks: manually defined categories have limited coverage and are difficult to update. When new domains are involved, the entity category system may need to be redefined.

In today's information age, it is challenging to manually define a complete category system for the massive entities on the internet. Therefore, obtaining entity concept categories dynamically from the web is essential. Dynamic mining methods have two primary characteristics:

Entities can belong to a wide range of categories without limitations, such as medications, animals, plants, events, conferences, dishes, and more, far exceeding traditional named entities. As society progresses, new categories may emerge, making it difficult for humans to determine a fixed and comprehensive category system.

The granularity of entity categories is finer and hierarchical. For example, organizational names in traditional named entities can be further divided into school names, company names, government department names, news agency names, etc. School names can then be subdivided into university names, high school names, primary school names, etc. These categories are connected through superordinate and subordinate relationships, forming a partial order structure.
In fact, there exist complex hierarchical relationships between entities and superordinate terms, as well as between superordinate terms themselves. Automatically constructing these fine-grained superordinate and subordinate hierarchical relationships can greatly benefit numerous intelligent service systems.


#### 2.2.1 Input and Output

**Input**

entity.txt: List of entities.
concept.txt: List of concepts (types).

**Output**

entity_concept.txt: Relationship between entities and concepts.
concept_concept.txt: Superordinate and subordinate relationships between concepts, where the former is a subconcept of the latter.

#### 2.1.2 Evaluation Metrics

This task utilizes precision (P), recall (R), and F1 score (F1-measure, F1) to evaluate the performance.


#### 2.2.3 Dataset

This task publicly releases around 20,000 entities and approximately 1,000 concepts. The task is designed as unsupervised, and therefore, no training set is provided. The test set is annotated by the organizers through automated entity type inference and manual verification, using a subset of a public dataset as the test set (around 500 entities and 500 concepts). The test set is not disclosed during the competition. The final results are evaluated by comparing the outputs submitted by participants with the manually annotated test set.


### 2.3 Subtask Three: Link Prediction in the COVID-19 Research Antiviral Drug Graph

Given the wide spread of the novel coronavirus and its significant impact on human health and socioeconomic aspects, the development of antiviral drugs has become crucial. At the core of a virus lie nucleic acid molecules (RNA or DNA) and a protein shell, which parasitize within a host and replicate through a series of steps. Antiviral drugs can target specific stages of viral replication to exert their antiviral effects. In the research and development of antiviral drugs, scientists need to conduct numerous biological experiments on various antiviral drugs to determine their viral inhibitory effects, a process that consumes considerable time. In the era of big data and artificial intelligence, leveraging vast clinical and experimental data enables the use of AI algorithms to predict the targeted effects of antiviral drugs on viruses, interactions between viral proteins and host proteins, and more.

The construction of an antiviral drug graph is one approach to address this issue. By building a knowledge graph of antiviral drugs, large-scale graph algorithms and knowledge reasoning can be employed to predict the targeted effects of antiviral drugs on viruses and the interactions between viral proteins and host proteins.

The antiviral drug graph is constructed based on the relationships between antiviral drugs, viruses, virus-related proteins, hosts, and host proteins. This graph can provide support for biological research on antiviral drugs, aiding in predicting the impact of antiviral drugs on viruses, interactions between viral proteins and human proteins, and other related issues. These problems hold significant practical significance and academic value for antiviral drug development and knowledge graph-based reasoning.

This task focuses on relationship prediction based on the antiviral drug graph, such as the targeted effects of drugs on viruses and interactions between proteins. Evaluation is based on the schema of the antiviral drug graph and the entities, entity properties, and relationships between entities in the knowledge graph to predict the relationships between two new entities. The evaluation does not restrict the models, algorithms, and technologies used by participating teams. Various graph algorithm models, pre-training methods, and other techniques can be employed for relationship prediction on the graph to collectively advance the development of knowledge graph technology.



#### 2.3.1 Input and Output

**Input**

schema.json: The schema of the knowledge graph, defining the entity types, attribute keys, and relationships between entities in the knowledge graph.

entities.json: List of entities including viruses, drugs, host proteins, viral proteins, etc.

attrs.json: List of entity attributes such as types of viruses, types of drugs, etc.

relationships.json: List of relationships between entities, such as virus-drug interactions, virus-viral protein relationships, viral protein-host protein relationships, etc.

link_prediction.json: Pairs of target entities or relationships to be evaluated.

**Output**

result.txt: For each missing entity relationship pair, the top 10 predicted sets of missing head or tail entities (sorted by likelihood from high to low). Participants are required to remove entity data with existing links in the training set from the queue to prevent occupation and wastage of queue positions.


#### 2.3.2 Evaluation Metrics

In this evaluation task, we adopt the Mean Reciprocal Rank (MRR) to assess the effectiveness of the construction. We consider various relationship predictions including virus-drug relationship prediction, protein-protein interaction prediction, virus-viral protein interaction prediction, etc., which collectively form the overall relationship prediction task.

#### 2.3.4 Dataset

For this task, the use of publicly available external knowledge bases is not permitted.

The dataset for this task comprises approximately 8,000 entities in total and around 50,000 triples. The data is sourced from structured data on reputable websites, with a training-to-testing set ratio of approximately 15:1.



### 2.4 Subtask Four: COVID-19 Knowledge Graph Question Answering Evaluation

This task falls under the category of Chinese Knowledge Base Question Answering (CKBQA) in the Chinese knowledge graph domain. In CKBQA, a Chinese question is provided as input, and the question-answering system selects entities or attribute values from a given knowledge base as answers. The questions are all objective factual questions without subjective factors. The process of understanding and answering these questions may involve subtasks such as entity recognition, relation extraction, semantic parsing, and more. While training these tasks can utilize additional resources, the final answers must come from the provided knowledge base.

Knowledge graph question answering holds strategic value and research significance in the current era of information explosion on the internet and the prevalence of artificial intelligence. Traditional search engines primarily focus on web resources, conducting searches and returning relevant web page links to users based on keyword indexing, text matching, and similar methods. However, users often seek specific answers to particular questions. Additionally, next-generation products such as smart speakers, intelligent medical consultations, and others often rely on specific knowledge graphs to respond to users' natural language requests. For instance, an intelligent medical consultation application can provide initial diagnoses based on a knowledge base in the medical and healthcare domain.

This knowledge graph question answering task is the third edition held on CCKS. Leveraging current events, we have carefully curated a dataset focused on health, medicine, disease prevention and control, centered around the COVID-19 open knowledge graph released on OpenKG. We have crafted a certain scale of question-answering data with a specific focus on health, medicine, disease prevention and control, using the COVID-19 pandemic as a starting point. While incorporating data from last year's open domain question answering task for model training, we expect participants' question-answering systems to handle a variety of encyclopedia-style shallow questions as well as deeper questions requiring domain-specific knowledge (such as infectious diseases).

The COVID-19 open knowledge graph used in this evaluation task is sourced from the COVID-19 topic on OpenKG (http://openkg.cn/group/coronavirus), encompassing multiple specific datasets related to health, prevention, encyclopedia, clinical data, and more. We have integrated these datasets together, along with the open domain knowledge base PKUBASE, as the basis for the question answering task.


#### 2.4.1 Input and Output

**Input**

The input file contains several lines of Chinese questions.

**Output**

The output file consists of a list of answers for each question, with elements separated by tabs (\t) on each line.


#### 2.4.2 Evaluation Metrics

The evaluation metrics for this task include Macro Precision, Macro Recall, and Averaged F1 score.


#### 2.4.3 Dataset

**Data Source**

The question-answering data for this evaluation is manually constructed and annotated. The annotation process does not rely on specific templates, and involves over 20 annotators to ensure diversity across various aspects of the questions. The questions in the question-answering dataset are not limited to a specific domain. They encompass both simple questions (corresponding to single tuple queries) and complex questions (corresponding to multiple tuple queries), with a rough ratio of 1:1.

**Training & Validation Sets**

During the training data release phase, we will provide around 3000 annotated data entries (including question/SPARQL/answer) as the training set. Additionally, we will release approximately 1000 questions without annotated results as the validation set. Participants can submit answers generated for their validation set, which will be evaluated by the competition system, scored, and ranked.

During the testing data release phase, we will provide the annotations for the validation set (including question/SPARQL/answer) and release around 1000 questions without annotated results for testing purposes.