# CHIP 2023 PromptCBLUE


## Task Description

Large Language Models (LLMs) represented by ChatGPT, GPT-4, and others have sparked a new wave of research in the field of natural language processing, demonstrating capabilities akin to Artificial General Intelligence (AGI) and attracting widespread attention in the industry. Against the backdrop of the popularity of LLMs, almost all NLP tasks have been transformed into prompt-based language generation tasks. However, in the Chinese medical NLP community, there is still no unified form of evaluation benchmark for tasks.

In order to promote the development and implementation of LLMs in the medical field, Professor Wang Xiaoling's team from East China Normal University, in collaboration with Alibaba Cloud Tianchi and experts and scholars such as Professor Tang Buchou from Harbin Institute of Technology (Shenzhen) Pengcheng Laboratory, has launched the PromptCBLUE-v2 evaluation benchmark. PromptCBLUE-v2 is a secondary development of the CBLUE benchmark, converting 18 different medical scenario NLP tasks into prompt-based language generation tasks, forming the first Chinese medical scenario LLM evaluation benchmark. This benchmark will help the open-source community and the industry quickly evaluate public or proprietary LLM models. PromptCBLUE-v2 will be one of the evaluation tasks of CHIP-2023, evaluated on the Tianchi competition platform.

To explore different technologies in the large model domain, we will open two leaderboards for the PromptCBLUE evaluation: (1) Non-fine-tuning track, where participants use the specified open-source large model backbone for predictions directly. Participants can enhance model performance by modifying prompts or adding demonstrations from the training set, and are allowed to fine-tune a sentence representation model with no more than 150 million parameters as assistance. (2) Parameter-efficient fine-tuning track, where participants can add a parameter-efficient fine-tuning module on top of the open-source large model backbone (the additional parameter volume must not exceed 1% of the large model backbone's parameter volume). Participants can only fine-tune the parameter-efficient fine-tuning module and are not allowed to fine-tune the large model backbone, using only one set of parameter-efficient fine-tuning modules to complete all tasks. When participating in either track, participants must select one open-source large model specified by the organizers.

The CHIP-PromptCBLUE-v2 evaluation task this time is a comprehensive upgrade of the CCKS-PromptCBLUE evaluation task:
- (1) More tasks: This edition of PromptCBLUE adds two challenging tasks from CBLUE, Text2DT and CMedCausal, which require a deep understanding of medical texts and have complex output forms, posing challenges for LLMs. Additionally, this PromptCBLUE edition includes the IMCS-V2-DAC task from the CCKS-PromptCBLUE evaluation task that was not scored.

- (2) Richer prompts: The number of prompt templates involved in the CCKS-PromptCBLUE test set is only 94. The number of templates for this CHIP-PromptCBLUE edition will exceed 450, placing higher demands on the robustness of LLMs.

- (3) Track settings: The CHIP-PromptCBLUE-v2 is divided into non-fine-tuning track and parameter-efficient fine-tuning track, examining different large model technologies such as in-context learning, prompt optimization, and parameter-efficient fine-tuning. The evaluation is fully dependent on the open-source large model community, assessing participants' innovative exploration and application capabilities in large model inference and fine-tuning technologies.


## Task Details

### Task One: CMeEE Task

Originally a standard medical text Named Entity Recognition (NER) task, participants are required to provide the specific span positions of medical entity mentions in the text to be extracted. In PromptCBLUE, this task has been transformed into: generating entity mentions based on the specified entity type. During scoring, we only consider the entity mentions and their type labels, no longer taking into account span position information.

### Task Two: CHIP-CDN Task

The prototype of this task involves providing a given original diagnostic term and requesting the corresponding standardized diagnostic term, which is selected from a standard vocabulary of over 40,000 terms in ICD-10. Since it is not feasible to input all forty thousand terms into an LLM at once, we have transformed the CDN task into: given the original term, selecting the matching term(s) from a number of candidate ICD-10 standardized diagnostic terms (there may be multiple matches, or none at all).



## Data Description

### Data Format

Under the PromptCBLUE task, we utilize over 450 prompt fine-tuning templates to transform various tasks from the CBLUE benchmark into a unified form based on prompt for response generation. After the transformation, all medical text NLP datasets will be converted into the following format. The input field represents the model's input, the target field represents the model's output, the type field indicates the original task type (not used as model input), and the answer_choices field contains options, which are only meaningful for classification, terminology standardization, and inference tasks.

```json
{
  "input": str,
  "target": str,
  "type": str,
  "answer_choices": Union[NoneType, List],
  "sample_id": str
}
```

In order to adapt various tasks from CBLUE into a format compatible with LLM input and output, we have made corresponding modifications to each dataset in CBLUE. The following two examples illustrate the input and output formats for the CMeEE task and CHIP-CDN task in PromptCBLUE. (For more details, please refer to the PromptCBLUE GitHub repository.)

### Data Example

#### Task One

```json
{
   "input": "医学实体识别：\n外周血白细胞计数常明显升高，伴核左移。\n实体选项：疾病，医学检验项目，医院科室，身体部位，微生物类，临床表现，药物\n格式规定：按照实体类型输出实体，每类实体的抽取结果输出形式为\”实体类型A：实体1，实体2\n\”\n答：",
   "target": "上述句子中的实体包含：\n医学检验项目实体：外周血白细胞计数\n疾病实体：\n医院科室实体：\n药物实体：\n微生物类实体：",
   "answer_choices": ["疾病", "医学检验项目", "医院科室", "身体部位", "微生物类", "临床表现", "药物"],
   "task_type": "ner",
   "task_dataset": "CMeEE-V2",
   "sample_id": "train-134372"
  }
```

#### Task Two
```json
{
   "input": "主动脉弓缩窄心功能低下\n归一化后的标准词是？\n实体选项：胫前动脉假性动脉瘤，主动脉缩窄，男性性腺功能低下，男性性腺功能低下，垂体功能低下，心功能不全\n说明：从候选的若干个ICD-10诊断标准词中选择出与原诊断描述匹配的词\n输出格式规定：直接输出合适的标准词，用逗号分隔\n答：",
   "target": "主动脉缩窄，心功能不全",
   "answer_choices": ["胫前动脉假性动脉瘤", "主动脉缩窄", "男性性腺功能低下", "男性性腺功能低下", "垂体功能低下", "心功能不全"],
   "task_type": "normalization",
   "task_dataset": "CHIP-CDN",
   "sample_id": "train-17932"
}
```


## Evaluation Guidelines

### Evaluation Data Release

The evaluation data will be released in two phases:

- August 10th:

Release training set and validation set, Test Set A (known as Test Set A). Baseline code and models will also be released for participants to quickly get started.
Test Set A does not contain answers. Participants need to make predictions on Test Set A and submit them to the evaluation platform to obtain scores, i.e., A-board scores.

- October 12th:

Release Test Set B, known as Test Set B. The final evaluation ranking will be based solely on the results from Test Set B.
The open evaluation period for Test Set B will be from October 12th, starting at 00:00, and ending at 17:59:59 on the same day.

### Submission Files

In PromptCBLUE, each task has been standardized into a unified format for generating responses based on prompts. Test samples are provided in the test.json file, formatted in JSON lines where each line is a JSON-serializable string. After serialization, the "input" field serves as the LLM input, and the "target" field is an empty string, to be filled in by the participants with model responses.

To submit for the test set and receive evaluation scores, participants need to provide three files:

- Participants need to submit the generated results of their trained LLM on the test set, named as test_predictions.json, in JSON-line format. The number of samples and their order should match the official test.json file.
- Participants should provide code to parse test_predictions.json and convert it into results.json, named as post_generate_process.py. This code should only use the Python standard library and can be run with the following command:

```bash
python post_generate_process.py test_predictions.json test_structured.json

```

- The results.json file can be loaded using the json.load() method and has the following structure:

```json
{
  "task_name": [
    {
      "sample_id": str,
      "answer": Union[str, dict]
    }
  ]
}
```

During the competition, participants are required to package the test_predictions.json file and post_generate_process.py file into a test_predictions.zip file for submission to the Tianchi platform's image for execution, resulting in the results.json file. It's important to note that in the zip file, do not add any folders; both files being packaged must be placed at the top level of the zip file.

The competition organizers will evaluate and score based on the results.json file generated within the Tianchi platform's image. Manually uploaded results.json files by participants will not be considered for scoring purposes.



## Evaluation Metrics

For this evaluation task, there is only one test set containing samples from multiple tasks. Evaluation will be conducted separately for each task using the following metrics:

- CMeEE-V2 and IMCS-V2-NER Tasks:
Strict micro Precision, Recall, and F1 scores based on entity instance level, which includes both the mention (all characters in the entity name) and the type of the entity.

- CMeIE and CMedCausal Tasks:
Strict micro Precision, Recall, and F1 scores based on triplet instance level, which includes the head entity mention, tail entity mention, and the relationship type.

- CHIP-CDEE Task:
Strict micro Precision, Recall, and F1 scores based on clinical event instance level, which includes the subject word, occurrence status, descriptive word, and anatomical site.

- IMCS-V2-SR and CHIP-MDCFNPC Tasks:
Strict micro Precision, Recall, and F1 scores based on clinical findings or symptom instances, including mention and positive/negative judgment label.

- CHIP-CDN Task:
Strict micro Precision, Recall, and F1 scores based on ICD-10 standard term instances, including mention and positive/negative judgment label.

- Text2DT Task:
Decision Tree Edit Ratio as the evaluation metric.

- CHIP-STS, KUAKE-QQR, KUAKE-IR, KUAKE-QTR Tasks:
Micro Precision, Recall, and F1 scores.

- CHIP-CTC, IMCS-V2-DAC, KUAKE-QIC Tasks:
Macro Precision, Recall, and F1 scores.

- MedDG and IMCS-V2-MRG Datasets:
Rouge-1, Rouge-2, and Rouge-L scores as evaluation metrics. Chinese characters in sentences will be separated by spaces before calculating Rouge scores to avoid tokenization impact. In the IMCS-V2-MRG task, generated diagnostic reports need to be split into six sections for Rouge score calculation: chief complaint, present illness, auxiliary examination, past history, diagnosis, and suggestions.

For each task, F1 (micro/macro), Rouge-L, or Tree_Edit_Ratio will be the primary metric.

**Overall Scoring:**

The overall score will be the average of F1 (micro/macro), Rouge-L, or Tree_Edit_Ratio scores for each task, which will be used for leaderboard ranking and awards.












