# CCKS 2021 CMRC

## Task Description

With the development of technology and economic progress, people are paying increasingly more attention to health issues. The dissemination of medical popular science information has also been widely recognized and valued by the country and society. Internet technology is advancing rapidly, with various new content forms such as graphics, text, Q&A, short videos, and live streams emerging continuously. How to utilize massive medical information to quickly meet user needs and ensure the accuracy and authority of content is an important topic.

Therefore, this evaluation task focuses on the understanding of Chinese medical popular science knowledge content and is divided into two subtasks:

- Medical Popular Science Knowledge Reading Comprehension
- Identification of Irrelevant Answers in Medical Popular Science Knowledge


## Subtask One: Medical Popular Science Knowledge Reading Comprehension

### 1. Task Definition

The task of medical popular science knowledge reading comprehension aims to find the corresponding answer snippets in related articles based on the search queries posed by users. These snippets serve as direct summaries to be displayed to the users.

This task references the CMRC2018 and CJRC2019 reading comprehension tasks:

- Reject Answer Definition: There is no snippet or summary in the article that can answer the query, resulting in a manually annotated empty result (0 annotated answers).

- Single Answer Definition: Each annotated answer is independently labeled by humans. A single answer can consist of a continuous text paragraph or multiple disjointed phrases/sentences/segments from the article. See section 2.2 for specific JSON format examples.
- Participants are required to predict at most 1 answer for each test data. If it is a reject answer, providing an empty result is sufficient.

### 2. Data Description

#### Format:
JSON file format.

- context_id: Document ID
- context_text: Main text content
- qas: List of question-answer pairs. Each includes:
  - query_text: Question description
  - query_id: Question ID
  - answers: List of answers, where: 
Each element is a string list representing a manually annotated answer.


#### Dataset Description

The dataset for this evaluation subtask includes:

- Training and Phase One Test Set: 27,000 annotated data points for training. 3,000 unannotated data points for the first phase test set.

- Final Test Set: During the test data release phase, there will be 6,000 unannotated data points for the final test set. The final test set is divided into two parts: public and private, each containing 3,000 data points. Public data serves as the ranking basis before the leaderboard is closed. Participating teams are required to submit results for the entire final test set each time. After the leaderboard is closed, the final ranking is calculated using predictions for all 6,000 data points in the final test set.

- Unannotated data in the dataset do not have an answers field.

- The training set contains 0 or 1 manually annotated answers, where 0 annotations indicate a 'reject' answer. The test set will contain 0 to 3 annotated answers. Having more than 1 annotated answer implies multiple correct annotations. When calculating evaluation metrics, the predicted result is compared with each annotated answer separately, and the highest F1 score is taken as the score for that result. The reason for multiple answers in the test set is that in real-world scenarios, different individuals may have varying understandings of the answer. Additionally, multiple annotators contribute to the annotations, and the highest matching score is considered.

- Apart from the training and test sets, the organizers will provide 100 sample annotated data points as the validation set (including metric calculation scripts). The validation set will contain 0 to 3 annotated answers. The evaluation results from the validation set will not be used for ranking purposes and cannot be included in the training set.


### 3. Evaluation Metrics

For this subtask, the performance of the predicted answers will be evaluated using the F1 score. The submission format for predicted data is the same as the training set, with each result containing 0 to 1 predicted answers.

The evaluation metric calculation script metrics.py will be released along with the training set.


## Subtask Two: Identification of Irrelevant Answers in Medical Popular Science Knowledge

### 1. Task Definition

In this subtask, the goal is to identify irrelevant answers in the context of medical popular science content in a question-answer format <Q, A>, where the answer A is not related to the question Q, meaning it does not address the question posed. In medical popular science content, there are generally two forms of irrelevant answers:

When the answer A and the question Q are completely unrelated, failing to address the question asked.
When the answer A and the question Q are related, but the direction of the answer is incorrect and does not address the question asked.
Examples:

**First Form:**

**Question:** Why does my face always break out in acne and appear red? How can I treat it?

**Description:** My face always breaks out in acne and appears red. What medication should I use?

**Answer:** The skin is bright red, likely due to an allergy to cosmetics. If the facial skin is thin, there may be a skin rash due to an allergy, so you should stop using cosmetics. Then apply calamine lotion. You can also take antiallergic drugs internally and avoid spicy foods, avoid staying up late, drink plenty of water. There is no special medicine. Pay attention to your diet and try loratadine.

**Annotation Comment:** The patient inquires about treating acne and medication, but the answer is about cosmetics allergies, lacking clear relevance.

**Second Form:**

**Question:** What is tracheal stenosis?

**Description:** My husband has been experiencing severe chest tightness recently and persistent coughing. After going to the hospital for examination, it was diagnosed as right upper lobe bronchial stenosis. I'm worried it might be cancer. Is right upper lobe bronchial stenosis cancer?

**Answer:** Generally, benign stenosis can often be treated with bronchoscopic balloon dilation. If it is a temporary stenosis, such as granulation caused by a tracheal foreign body leading to stenosis, after removing the tracheal foreign body through bronchoscopy, the granulation can disappear quickly. If it is malignant stenosis, malignant stenosis mainly refers to tumors, the treatment is more complex. In addition to whether the tumor can be removed and whether it can be treated surgically, bronchoscopic intervention therapy should also be considered.

**Annotation Comment:** The patient asks about the cause of tracheal stenosis, but the answer provides information on the treatment of tracheal stenosis, showing an incorrect direction in the response

### 2. Data Description

**2.1 Format:**

**Label:** Annotation, 0/1, where 1 indicates that the answer cannot address the question (irrelevant answer).

**Docid:** Document ID

**Question:** Question

**Description:** Additional description related to the question

**Answer:** Response


**2.2 Example:**

**Label:** 1

**Docid:** abcd023659647xigos

**Question:** How to treat paronychia with granulation tissue?

**Description:** The paronychia has granulation tissue, about the size of a soybean. Currently using iodine and erythromycin ointment, with little effect. Besides nail extraction surgery, are there any better treatment methods?

**Answer:** From what you described, this is a local strut that didn't grow well. Also, if you have paronychia, you need to treat the paronychia first before pulling the nail. If the nail is embedded in the flesh, you must first remove the nail. If you don't remove the nail, you can only reduce inflammation first. In the future, when the nail grows out, it will cause paronychia again.


**2.3 Dataset Information**

The dataset for this evaluation subtask includes:

- Training and Phase One Test Set: 40,000 annotated data points as the training set (roughly 1:2 positive to negative ratio). 5,000 unannotated data points serve as the Phase One test set, used for ranking before the final test set release. Submission format aligns with the training set. For offline optimization, you can use the training set for n-fold cross-validation.

- Final Test Set: During the test data release phase, there will be 10,000 unannotated data points as the final test set. It is split into public and private domain data (each with 5,000 points). Public domain data is for rankings before the leaderboard closure, where each team needs to submit results for the entire final test set. After the closure, the final ranking uses predictions for the entire final test set (10,000 points).

- Annotation Data Format: Each line in the annotated data represents one data point with 5 columns separated by tabs: Label, Docid, Question, Description, and Answer. Unannotated data format includes 4 columns separated by tabs: Docid, Question, Description, and Answer.

### 3. Evaluation Metrics

For this subtask, the evaluation metric includes: Precision (P), Recall (R),F1 Score (F1), These metrics are used to evaluate the effectiveness of identifying irrelevant answers in the context of the task.


