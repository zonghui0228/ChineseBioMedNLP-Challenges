# CHIP 2018 STS

## Task Description

The Ping An Medical Technology Intelligent Patient Health Consultation Sentence Matching Competition is a real-world sentence intent matching task provided with linguistic support by Ping An Medical Technology and organized by them.
Sentence matching is one of the most basic tasks in natural language processing and serves as the foundation for various tasks such as automatic question answering, chatbots, information retrieval, and machine translation. The purpose of sentence matching problems is to determine whether two sentences are semantically equivalent. Semantic equivalence determination mainly relies on the intent implied by the sentences (mainly questions) to judge whether two sentences are equivalent, rather than directly determining whether they express the same semantics. Therefore, the core lies in intent matching of sentences. Due to the origin from a real question and answer corpus, this task is more closely related to the actual requirements of natural language processing tasks like intelligent customer service.

The main goal of this evaluation task is to match the intents of real Chinese patient health consultation sentences. Given two sentences, the requirement is to determine whether their intents are the same or similar. All the data come from real patient questions on the internet and have been filtered and manually annotated for intent matching. Ping An Cloud will provide GPU training environments for the participating teams.


## File Description

The files provided to the participants consist of five files: question_id.csv, word_embedding, char_embedding, train.csv, and test.csv. question_id.csv contains de-identified questions along with their IDs, in both segmented word and character forms (including punctuation). word_embedding and char_embedding are pre-trained embeddings for words and characters, respectively (processed for de-identification).

train.csv and test.csv serve as the training and testing sets, comprising pairs of question IDs. The label field indicates whether the semantics between the questions are the same. If they are the same, it is labeled as 1; if not, it is labeled as 0. The labels are known for the training set but unknown for the testing set.

**Input:** A pair of sentences

**Output:** A binary label (0 or 1) indicating whether the pair of sentences express the same or similar intent.

**Example:**

**Example 1**

Input: 糖尿病患者如何锻炼\t糖尿病人怎么运动

Output: 1

**Example 2**

Input: 糖尿病肾病有什么危害\t糖尿病有什么危害

Output: 0


## Evaluation Metrics

The evaluation metrics for this task include Macro Precision, Macro Recall, and Averaged F1 score.



## Dataset

### Data Source

The main source of the evaluation data is from manual construction and annotation.

### Training Set & Validation Set

During the data release phase, we will publish around 20,000 annotated data (processed for desensitization, including punctuation) as training data for participants to use for training and testing. Additionally, around 10,000 data points without labeled results will be released as a validation set.








