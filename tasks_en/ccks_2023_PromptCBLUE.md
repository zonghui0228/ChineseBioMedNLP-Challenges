# CCKS 2023 PromptCBLUE


## Overview of the Competition

The surge of research in the field of natural language processing has been sparked by large language models (LLMs) like ChatGPT and GPT-4, showcasing capabilities akin to general artificial intelligence (AGI) and garnering widespread attention in the industry. With LLMs dominating the scene, nearly all NLP tasks have evolved into prompt-based language generation tasks. However, within the Chinese medical NLP community, there lacks a unified task format for benchmarking. To propel the development and implementation of LLMs in the medical field, Professor Wang Xiaoling's team from East China Normal University, in collaboration with the Tianchi team, has introduced the PromptCBLUE benchmark. This benchmark is an adaptation of the CBLUE benchmark, transforming 16 different medical scenario NLP tasks into prompt-based language generation tasks, establishing the first Chinese medical scenario LLM benchmark.

PromptCBLUE will be featured as one of the evaluation tasks at CCKS-2023, hosted on the Tianchi competition platform. Considering the potential involvement of commercial data in current LLM training and the constraints on open-sourcing large-scale models, PromptCBLUE evaluation will be open in two tracks:

General Track: Open for evaluation of self-developed LLMs from enterprises, universities, open-source communities, research teams, or individuals.
Open Source Track: Accepting evaluation submissions from various teams, provided they utilize open-source large model frameworks and exclusively train/fine-tune using open-source datasets or datasets that can be fully submitted to the competition organizers for review.

## Task Overview
With ChatGPT and GPT-4 leading a new wave of artificial intelligence revolution worldwide, nations, institutions, and companies are fervently developing their own large-scale language models. Simultaneously, the active deployment of large models in various vertical domains has become a topic of significant discussion in academia and industry. To facilitate the implementation of Chinese large models (or models that support Chinese) in the medical domain, a unified and comprehensive evaluation benchmark is indispensable. Professor Wang Xiaoling's team from East China Normal University, in collaboration with the Tianchi team, has introduced the PromptCBLUE benchmark. This benchmark is an enhanced version of the CBLUE benchmark, converting 16 different medical scenario NLP tasks into prompt-based language generation tasks, establishing the first Chinese medical scenario LLM benchmark.

## Task Objective
We utilize 94 instruction fine-tuning templates to adapt various tasks within the CBLUE benchmark. Post-transformation, medical text NLP datasets will be converted into the following format. The "input" field string represents the input for the LLM model, while the "target" field, also a string, signifies the text sequence that the LLM model is required to generate. Additional information includes the "type" indicating the original task type (not used as model input), "answer_choices" field containing options (only relevant for classification, terminology standardization, and inference tasks), and "sample_id" serving as the sample identifier. These additional details are not part of the LLM input.

```json
{
    "input":  str,
    "target":  str,
    "type":  str,
    "answer_choices":  str,
    "sample_id":  str,
}
```
To align various tasks from CBLUE into a format suitable for LLM input and output, we have modified each dataset within CBLUE accordingly. For more details, refer to the CBLUE Task Transformation documentation.

## Evaluation Data Release

The evaluation data for this competition will be released in two phases:

- May 10th: The training set, validation set, and Test Set A will be released. Baseline code and models will also be provided for participants to quickly get started. Test Set A does not contain answers; participants are required to make predictions on Test Set A and submit them to the evaluation platform to obtain scores, i.e., A-board scores.

- July 14th: Test Set B, also known as the B-board test set, will be released. The final evaluation ranking will be based solely on the results from Test Set B. The open evaluation period for Test Set B will run from July 14th to July 17th, ending at 17:59:59.

The sample statistics for each set are as follows:

| PromptCBLUE | - |
|---|---|
|Version | v0.1 |
|Number of prompt templates | 94 |
|Training set | 68500 |
|Validation set | 10270 |
|Test Set A | 10270 |
|Test Set B | 10270 |

It's worth noting that in the datasets we provide, we have utilized 94 instruction fine-tuning templates. Participants can use other templates or instructions generated based on models like ChatGPT for training on the training data.

## Evaluation Metrics

In this evaluation task, although there is only one test set containing samples from multiple tasks, we will evaluate each task separately using specific scoring methods. The evaluation metrics for each task are as follows:

- For CMeEE-V2 and IMCS-V2-NER tasks: Strict, micro Precision, Recall, and F1 scores based on entity instance level. An entity instance includes both the mention (all characters of the entity name) and the type. In this context, "strict" implies that the model must correctly predict both the mention and type of the entity instance in the ground truth on the specified sample_id to be considered a successful prediction (TP +1). If the model predicts an entity instance not in the ground truth, it's counted as a false positive (FP +1). If the model fails to predict an entity instance in the ground truth, it's counted as a false negative (FN +1). The Precision, Recall, and F1 scores are then calculated based on TP, FP, and FN across the entire test set.

- For CMeIE task: Strict, micro Precision, Recall, and F1 scores based on triplet instance level. A triplet instance includes the head entity mention, tail entity mention, and relation type fields.

- For CHIP-CDEE task: Strict, micro Precision, Recall, and F1 scores based on clinical event instance level. A clinical event instance includes the subject term, occurrence status, descriptor term, and anatomical site fields.

- For IMCS-V2-SR and CHIP-MDCFNPC tasks: Strict, micro Precision, Recall, and F1 scores based on clinical finding or symptom instance level. A clinical finding or symptom instance includes mention and positive/negative judgment label fields.

- For CHIP-CDN task: Strict, micro Precision, Recall, and F1 scores based on ICD-10 standard term instance level. An ICD-10 standard term instance includes mention and positive/negative judgment label fields.

- For CHIP-STS, KUAKE-QQR, KUAKE-IR, and KUAKE-QTR tasks: Micro Precision, Recall, and F1 scores will be used as evaluation metrics. For CHIP-CTC, IMCS-V2-DAC, KUAKE-QIC, Macro Precision, Recall, and F1 scores will be used as evaluation metrics.

- For MedDG and IMCS-V2-MRG datasets: Rouge-1, Rouge-2, and Rouge-L scores will be used as evaluation metrics. To avoid tokenization effects, Chinese characters in sentences will be split and separated by spaces before calculating Rouge scores. In the IMCS-V2-MRG task, the model-generated diagnostic report needs to be split into six sections: chief complaint, present illness history, auxiliary examination, past medical history, diagnosis, and suggestions, with Rouge scores calculated for each section and then averaged.

In each task mentioned above, F1 (micro/macro) or Rouge-L will serve as the primary metric for evaluation.

Overall scoring calculation: The F1 (micro/macro) or Rouge-L scores for each task will be averaged to obtain an overall score, which will be used as the basis for leaderboard ranking and award evaluation.