# CHIP 2021 MDCFNPC

## Task Overview

Clinical Finding is a concept set describing the patient's condition under clinical medicine. Each concept of clinical finding has a clear meaning (such as diarrhea, vomiting, high temperature, physical cooling, cooling drug therapy). In order to ensure rigor, medicine has provided clear definitions and explanations for each concept.

A medical clinical report is a summary description of the patient's condition. To provide as comprehensive and accurate an objective description of the patient's condition as possible, it is necessary to use rigorous concepts of clinical findings to express the patient's condition. The most basic states are negative and positive, indicating whether a specific clinical finding exists or occurs in the patient.

Currently, in internet healthcare, patients may describe their symptoms in an informal way, commonly referred to as chief complaints. Meanwhile, doctors conduct targeted inquiries to refine and supplement these chief complaints. In the context of internet healthcare dialogues, the Alibaba Quark team plans to conduct a series of academic evaluation tasks at the CHIP conference. This evaluation is the first phase, focusing on the classification of positive and negative clinical findings in internet online consultation records.

## Task Details

The annotation data for this task is sourced entirely from the public data of Chunyu Doctor's internet online consultations. Positive and negative are generally defined in the patient's chief complaint description and the doctor's diagnostic discrimination. The SOAP (Subjective, Objective, Assessment, Plan) evaluation record method is currently the most commonly used problem-oriented medical recording method internationally. The discrimination of positive and negative primarily involves entities related to S and A. Data preprocessing involves first aligning for SOAP classification, then identifying NER for S and A, followed by annotation of positive and negative based on this. Note: Not all NER parts of clinical findings in the dialogue need to be identified and annotated, only those that describe the patient's objective and subjective clinical findings and corresponding diagnostic results.


## Positive and Negative Annotation Standards

### Annotation Attributes

Negative (neg), Positive (pos), Other (other), Not annotated (empty)

### Annotation Criteria

There are four categories in total. This phase of evaluation involves dialogues, interactions between doctors and patients regarding symptoms/diseases, considering contextual connections and logical relationships to determine the positivity/negativity of symptoms and "other" (typically when the user has not responded, or the response is unclear, or unknown).

- Positive (pos): Related to existing symptoms/illnesses, doctor's diagnosis (including multiple diagnostic conclusions), and hypothetical future illnesses, e.g., "If left untreated, it will likely lead to Disease A," where "Disease A" is labeled as positive.
- Negative (neg): Not related to symptoms of any illness.
- Other (other): Unknown annotations; generally, when the user has not responded, does not know, or the response is unclear/ambiguous and difficult to infer.
- Not annotated (empty): No practical significance for annotation; typically when the doctor's explanation relates to general knowledge, or conditions independent of the patient's current status, or when certain examination items include disease names that are not relevant for annotation (e.g., "Hepatitis B panel/Hepatitis B antibodies," disease names mentioned in drug names are not annotated).

### Annotation Examples

Example 1
```
patient： 医生您好，从昨天晚上开始 肚子一直疼， ，吃了布洛芬有所缓解。---- “肚子一直疼”标记 阳性
doctor： 肚子疼， 是 上腹部疼 么？---- “肚子疼”标记 阳性 ，是基于上文推断；“上腹部疼”标记 阴性 ，基于下文推断。
patient： 不是，主要是 下腹部疼 。---- “下腹部疼”标记 阳性 ;
doctor： 是 针扎样的疼 么？---- “针扎样的疼”标注 其他 ;
patient： 不知道，描述不出来， 有点抽筋的那种疼 。 ---- “针扎样的疼”标注 其他 ;
……
doctor： 这种情况考虑为急性肠胃炎导致的，急性肠胃炎可能除了 腹疼 之外，可能还会引起 腹泻 等，需要即时补充水分。---- “腹疼”和“腹泻”均标注为 不标注 ，是医生解释医学常识。
```

Example 2
```
doctor： 有 尿急尿频 吗？ ----“尿急”、“尿频”标注 阳性
patient： 有点。

```

Example 3：

```
doctor： 请问 白带有异味 吗？ 外阴痒 吗？----“白带有异味”标注 阳性 、“外阴痒”标注 阴性
patient： 外阴在一个月之前有些发 痒 ，但是现在不 痒 ，白带闻起来有点腥臭味----第一处“痒”标注 阳性 ， 第二处“痒”标注 阴性
```

Example 4：

```
doctor： 有 头晕 呕吐吗？----“头晕”标注 其他
patient： 不确定是不是 头晕 ，感觉不 头晕 但好像又是 头晕 ---- 三个“头晕”均标注 其他 ，用户的回答模棱两可不好判断，标注“其他”
```

Example 5：

```
doctor： 腹泻 几次了？有 呕吐腹痛 吗？----“腹泻”标 阳性 ，“呕吐”- 阳性 “腹痛”- 阳性
patient： 从昨天到今天三四次，也没敢吃东西，吃点就要去厕所，其他都还好，昨天吃了不新鲜的水果，
patient： 吃完过一会儿就 肚子痛 ，没 吐 ，晚上喝点粥不知道能不能好点---- “肚子痛”标 阳性 ，“吐”标 阴性
```


Example 6：

```
patient： 坐起来就不怎么 痛 ，躺着就 痛 ，站着不动也不怎么 痛 ，走路慢点也还好，快点就 痛 ----四个“痛”，分别标注 阴性 ， 阳性 ， 阴性 和 阳性
```

Example 7：

```
patient： 我前天打篮球扭到了脚踝，现在脚踝处很 疼 ，并且已经 肿 了，该怎么治疗
doctor： 你这属于踝关节扭伤，现在需要消 肿 ，止 痛 治疗； ----“肿”、“痛”均标注 阳性
```


Example 8：
```
patient： 我害怕是 糖尿病 。----“糖尿病”标注 阴性 ，
doctor： 你这个不是 糖尿病 ，这种情况考虑是 肠炎，肠胃炎 。可以服用一些治疗 肠炎 药物，如康恩贝 肠炎 宁胶囊；----“糖尿病”标记 阴性 ，第一个“肠炎”，“肠胃炎”均标注 阳性 ，第二、三个“肠炎”均标记为 不标注
```

### Data Format Description:

The data is provided in JSON format and includes the following fields:

- text: Paragraph text
- sender: Patient or doctor
- NER: Entity recognition and positive/negative labels
  - mention: Field matching entities appearing in the text
  - name: Standard name corresponding to the mention. Note: Not all mentions have corresponding standard names.
  - range: Range of the mention in the sentence
  - type: Entity type, standardized as "clinical_findings," no longer distinguishing between symptoms or diseases
  - attr: Negative/Positive/Other/Not annotated

For this evaluation, a total of 6000 dialogue corpora are provided as the training set. The testing is divided into two stages, A and B lists, each providing 2000 dialogues for testing data. The submission time for the B list will be limited to within 48 hours.


## Evaluation Metrics:

For the testing data, only the prediction of the "attr" field is required. This evaluation will use Macro-F1 as the evaluation metric.

















