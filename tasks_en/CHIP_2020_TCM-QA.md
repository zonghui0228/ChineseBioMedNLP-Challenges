# CHIP 2020 TCM-QA


## Task Introduction

With the continuous development of natural language processing technologies, Question Generation has been implemented in many practical scenarios (such as in the field of medicine, where it can be applied to scenarios like automatic inquiry and assisting in diagnosis). Through machine-initiated questioning, it is possible to efficiently build or supplement knowledge bases and expand dataset sizes. Fueled by the epidemic, artificial intelligence is continuously assisting in the accelerated development of traditional Chinese medicine inheritance and innovation. Against this backdrop, a "question generation" challenge task focused on traditional Chinese medicine texts has been established.

## Task Details

The annotation data for this task all comes from texts in the field of traditional Chinese medicine, including translations of the "Yellow Emperor's Inner Canon," the "Famous Doctor Encyclopedia - Traditional Chinese Medicine," the "Chinese Patent Medicine Volume," and some texts from chronic disease health knowledge forums. A total of 13,000 pairs of (question, document, answer) were annotated from 5000 documents, with each document manually generating 1 to 4 pairs of (question, answer). The types of questions include entity-based and descriptive-based questions (yes/no questions are included in the descriptive-based category). The "questions" are all manually annotated, while the "answers" are continuous segments from the documents. This task is supported by Alibaba Cloud Tianchi platform, with 3500 corpora and their annotated data made available for training, 750 corpora available for initial evaluation, and the remaining 750 test data used for final evaluation. The test data will not be made available for download, and participants in the final stage must submit their models to the Tianchi operating environment for online evaluation according to the official requirements of the Alibaba Tianchi platform.


## Data Description


**Example**

```json
{
        "id": 98,
        "text": "黄帝道：什麽叫重实？岐伯说：所谓重实，如大热病人，邪气甚热，而脉象又盛满，内外俱实，便叫重实",
        "annotations": [
        {
        "Q": "重实是指什么？",
        "A": "所谓重实，如大热病人，邪气甚热，而脉象又盛满，内外俱实，便叫重实"
        },
        {
        "Q": "重实之人的脉象是什么样？",
        "A": "脉象又盛满"
        }
        ],
        "source": "黄帝内经翻译版"
        },
```

```json
        {
        "id": 714,
        "text":
        "葡萄胎：表现为剧烈恶心呕吐，阴道不规则流血，偶有水泡状胎块排出。子宫质软大多较停经月份大。妊娠合并急性胃肠炎：多有饮食不洁史，不仅有恶心呕吐，还常伴有腹痛、腹泻等胃肠道症状。孕痈：即妊娠期急性阑尾炎，表现为脐周或中上腹部疼痛，伴有恶心、呕吐，24小时内腹痛可转移到右下腹。",
        "annotations": [
        {
        "Q": "葡萄胎有什么症状表现？",
        "A": "表现为剧烈恶心呕吐，阴道不规则流血，偶有水泡状胎块排出。子宫质软大多较停经月份大。"
        },
        {
        "Q": "孕痈有什么表现？",
        "A": "表现为脐周或中上腹部疼痛，伴有恶心、呕吐，24小时内腹痛可转移到右下腹。"
        },
        {
        "Q": "孕痈有其它叫法吗？",
        "A": "妊娠期急性阑尾炎"
        }
        ],
        "source": "名医百科中医篇"
        },

```

```json
        {
        "id": 1078,
        "text":
        "发热是小儿最常见的临床症状，是机体抵抗疾病的一种防御性反应，家长不必惊慌，也不要一发热就吃退热药，这样反而会影响疾病的诊断，也不利于炎症的控制，要掌握以下几点：\n（1）首先找一找原因。小婴儿在夏季是否衣服太多，包得太严，喂水太少等。也可以查一查耳朵内、脖子及全身皮肤（肛门周围）有无发红、发肿、疖子等。\n（2）可给予降温处理。解开衣服，让散热增加。用38℃的温水擦浴20分钟。也可用75%酒精加水一半（为30%酒精）擦腋下、腹股沟、颈部。也可用热水袋内加水和冰块，枕于头下，或冷水毛巾敷于额头部。\n（3）如体温不降，烦躁不安，应去医院治疗。\n（4）发热时，要多喂水，多喂易消化、清淡的食物，如咽喉红肿疼痛，喂凉饮食可减轻疼痛。体温下降后，要注意保暖和营养的摄入。",
        "annotations": [
        {
        "Q": "小儿发热能否必须吃退烧药？",
        "A": "发热是小儿最常见的临床症状，是机体抵抗疾病的一种防御性反应，家长不必惊慌，也不要一发热就吃退热药，这样反而会影响疾病的诊断，也不利于炎症的控制。"
        },
        {
        "Q": "小儿发热要掌握哪几点？",
        "A":
        "（1）首先找一找原因。小婴儿在夏季是否衣服太多，包得太严，喂水太少等。也可以查一查耳朵内、脖子及全身皮肤（肛门周围）有无发红、发肿、疖子等。（2）可给予降温处理。解开衣服，让散热增加。用38℃的温水擦浴20分钟。也可用75%酒精加水一半（为30%酒精）擦腋下、腹股沟、颈部。也可用热水袋内加水和冰块，枕于头下，或冷水毛巾敷于额头部。（3）如体温不降，烦躁不安，应去医院治疗。（4）发热时，要多喂水，多喂易消化、清淡的食物，如咽喉红肿疼痛，喂凉饮食可减轻疼痛。体温下降后，要注意保暖和营养的摄入。"
        },
        {
        "Q": "小儿发热什么情况下要去看医生？",
        "A": "体温不降，烦躁不安，应去医院治疗。"
        }
        ],
        "source": "慢性病养生保健科普知识"
        },
```

- Data Format Description: Provided in JSON format, including the following fields:
  - id: Paragraph ID
  - text: Paragraph Text
  - annotations: Array containing multiple pairs of (question, answer)
    - Q: Question
    - A: Answer


## Evaluation Metrics

This evaluation will be based on ROUGE-L and BLUE-4. In cases where the ROUGE-L scores are the same, the BLUE-4 scores will be compared.


