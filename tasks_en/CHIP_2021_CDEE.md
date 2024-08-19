# CHIP 2021 CDEE


## Task Overview:

Clinical findings refer to the manifestations of diseases, encompassing a patient's discomfort and abnormal manifestations detected through examinations, primarily including symptoms and signs.

Clinical finding event extraction is a task in medical data processing that involves extracting the attributes of clinical finding events from medical records, including the anatomical site, subject term, descriptor term, and occurrence status.

## Task Details:

The main objective of this evaluation task is to extract clinical finding events from Chinese electronic medical records. Given a segment of current medical history or an imaging report, the task requires extracting the four attributes of a clinical finding event. All data is sourced from real medical records. (Note: Due to potential modifications made to the original sentences in the data, sometimes the calculation of offsets may not be precise, so textual position information (position) has not been provided. If needed, it can be provided.)


## Data Description

An example of the data is as follows:

| core_name     | tendency    | character                            | anatomy_list |
|---------------|-------------|--------------------------------------|--------------|
| 疼痛          |             |                               |     ["头"]          |
| 疼痛          |             | ["持续性跳痛", "中-重度", "可缓解"] | ["头"]       |
| 恶心          | 否定        |                                      |              |
| 呕吐          | 否定        |                                      |              |
| 视物模糊      | 否定        |                                      | ["眼"]       |
| 麻木          | 否定        |                                      | ["肢体"]     |
| 无力          |             |                                      | ["肢体"]     |
| 疼痛          |             |                                |     ["头"]         |
| 疼痛          | 不确定      | ["血管性"]                           | ["头"]       |
| 食欲          |             | ["正常"]                             |              |
| 神志          |             | ["清醒"]                             |              |
| 精神          |             | ["尚可"]                             |              |
| 睡眠          |             | ["尚可"]                             |              |
| 大便          |             | ["正常"]                             |              |
| 排尿          |             | ["正常"]                             |              |
| 体重          |             | ["无明显变化"]                       |              |


```
入院前2+年，患者无明显诱因出现剑突下疼痛，伴嗳气、反酸，有咳嗽、咳痰伴胸背部疼痛，呈胀痛，评分：7分，无加重缓解因素，无胸闷、咯血、呼吸困难，无潮热、盗汗、疲乏、消瘦，无畏寒、发热，于我院消化内科就诊，完善胸部ct：左肺下叶软组织块块影，考虑肺ca；遂转入我科。
```

| core_name | tendency | character                            | anatomy_list          |
|-----------|----------|--------------------------------------|-----------------------|
| 疼痛      |          |                           |       ["剑突下"]                |
| 嗳气      |          |                                      |                       |
| 反酸      |          |                                      |                       |
| 咳嗽      |          |                                      |                       |
| 咳痰      |          |                                      |                       |
| 疼痛      |          |                           |        ["胸背部"]               |
| 胀痛      |          | ["评分：7分"，"无加重缓解因素"]     | ["胸背部"]           |
| 胸闷      | 否定     |                                      | ["胸"]               |
| 咯血      | 否定     |                                      |                       |
| 呼吸困难  | 否定     |                                      |                       |
| 潮热      | 否定     |                                      |                       |
| 盗汗      | 否定     |                                      |                       |
| 疲乏      | 否定     |                                      |                       |
| 消瘦      | 否定     |                                      |                       |
| 畏寒      | 否定     |                                      |                       |
| 发热      | 否定     |                                      |                       |
| 块影      |          |                 |         ["左肺下叶软组织"]              |


## Evaluation Metrics

Each text may have multiple attribute entities for one event property. The evaluation metrics use event attributes to calculate precision and recall, requiring all attributes to be completely correct to calculate the F1 score.
