# CHIP 2020 Covid19


## Task Description

Since the initial public report of pneumonia cases in Wuhan on December 31, 2019, the novel coronavirus has spread rapidly nationwide, prompting governments to quickly initiate emergency responses. Normal life and socio-economic activities have been severely disrupted. After half a month, the United States confirmed its first case of COVID-19, leading to a rapid global outbreak. As of today, there have been a cumulative 20 million confirmed cases of COVID-19 worldwide, with 750,000 deaths and nearly 300,000 new cases reported daily. In the absence of vaccines and specific treatments, countries have implemented various control measures to reduce virus transmission caused by human contact. Since the outbreak, experts and scholars in the field of public health have been providing important predictions on future trends of the COVID-19 pandemic, which serve as crucial references for decision-makers.

## Task Details

The goal of this evaluation task is to predict the number of daily new confirmed COVID-19 cases in a specific region based on publicly available daily statistics of newly confirmed patients.

### Predictive Principles:

The time-series data are authentic historical data and have not been manipulated.

### Input/Output:

**Input:** Historical data from a specific region. The date range starts from the date of the first confirmed case up to mid-August 2020, with the observation statistic dimension being the daily number of new confirmed cases (or combined with provided feature data, the choice to use it is optional).

**Output:** The number of daily new confirmed cases within a future time period.


## Data Overview

Three typical regional time-series datasets of confirmed cases:

The source data are all from the same publicly available website. They have not been modified.
Each dataset samples a typical region, spanning over 4 months or more, with the daily number of new confirmed cases as the statistical value. The implemented preventive measures are those related management measures announced by the government in that region.
This task provides a total of three typical regional time-series datasets.

- Example:

| 日期       | 每日确诊人数 | 防疫措施                               |
|------------|--------------|----------------------------------------|
| 2020/3/8   | 25           |                                        |
| 2020/3/9   | 56           | 开始投入核酸检测                      |
| ...        | ...          | ...                                    |
| 2020/4/31  | 320          | 建议部分区域企业可实行远程在家办公    |
| ...        | ...          | ...                                    |
| 2020/5/5   | 371          | 公众活动取消、禁止人群聚集、学校关闭 |
| ...        | ...          | ...                                    |
| 2020/5/28  | 600          | 禁止部分国家入境                      |


- Feature Data: Feature description for each regional data, an example is as follows.

|       Attribute       |   Value   |
|-----------------------|-----------|
| Total Population      |  106000   |
| GDP per Capita        |  25000    |
| Elderly Population %  |  13.55    |
| ...                   |    ...    |


## Evaluation Metrics

Due to the nature of the source data being updated daily in real-time, the test data will compare the predicted results within a future week (7 days) with the actual published confirmed data.







