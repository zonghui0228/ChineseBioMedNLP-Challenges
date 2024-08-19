# CHIP 2019 STS

## Task Description

Transfer learning is an important component in natural language processing, aimed at improving the learning effectiveness of new tasks by transferring knowledge from related tasks that have already been learned, thereby enhancing the model's generalization ability.
The main goal of this evaluation task is to perform transfer learning among different disease types based on Chinese disease-related question and answer data. Specifically, given pairs of questions from five different disease types, the task is to determine whether the semantic meanings of the two sentences are the same or similar. All the data come from real patient questions on the internet, and have been filtered and annotated with human intent matching.

## File Description

The files provided to the participants consist of three files: train.csv, dev.csv, and test.csv. train.csv is the training set, containing 20,000 pairs of manually labeled disease-related question and answer data from five disease types, with 10,000 pairs for diabetes, and 2,500 pairs each for hypertension, hepatitis, AIDS, and breast cancer. dev.csv is the validation set, consisting of 10,000 unlabeled pairs of disease-related question and answer data from the same five disease types, with 2,000 pairs each. test.csv is the test set, containing 50,000 pairs of manually labeled disease-related question and answer data, with only some data available for validation.

The 'category' column represents the disease type of the question pairs, corresponding to: diabetes, hypertension, hepatitis, AIDS, and breast_cancer. The 'label' column indicates whether the semantics of the question pairs are the same. If they are the same, it is labeled as 1; if not, it is labeled as 0. The labels are known for the training set, while they are unknown for the validation and test sets.



### Example

```
question 1：糖尿病吃什么？

question 2：糖尿病的食谱？

label:1

```
```
question 1：乙肝小三阳的危害？

question 2：乙肝大三阳的危害？

label:0
```

## Evaluation Metrics

The evaluation metrics for this task include Precision, Recall, and F1 score. The final ranking is based on the F1 score.


## Dataset:

The data for this evaluation mainly comes from manual construction and annotation.

The training set contains 20,000 pairs of labeled data, the validation set contains 10,000 pairs of unlabeled data for participants to use for training and validation. The test set contains 50,000 pairs of unlabeled data, with only a portion of the data available for validation. Participants are required to predict labels for the test set data and submit them.

The validation set data serves as the evaluation basis for Leaderboard A, while the test set data serves as the final evaluation basis for Leaderboard B.

