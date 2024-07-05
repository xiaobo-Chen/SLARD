# **SLARD: A Chinese Superior Legal Article Retrieval Dataset**
## Overview
SLARD is the first Chinese superior legal articles retrieval dataset. It includes 2,627 query articles and 9,183 candidate articles, selected from 3 million currently valid regulations, covering 31 law categories. Each entry in the dataset has been manually annotated twice to ensure accuracy and reliability. We hope this dataset will facilitate legislators in scientific legislation and promote the development of related research.

## Dataset Explanation
### Query
{
        "query_id": 3,
        "clause_content": "市、区县人民政府应当建立完善招标投标工作监督机制,推进招标投标信用制度建设和信息化建设。市、区县人民政府发展改革部门负责指导和协调本行政区域的招标投标工作。市、区县人民政府有关行政监督部门按照职责分工对招标投标活动实施监督,依法查处招标投标活动中的违法行为。财政部门依法对实行招标投标的政府采购工程建设项目的预算执行情况和政府采购政策执行情况实施监督。行政监察部门依法对参与招标投标活动的行政监察对象实施监察。"
        "main_mean": "建立招投标监管体系",
        "regulations_id": 310,
        "title": "淄博市招标投标条例"
        "superior_law_regulations_id": [
            206
        ],
        "category": "工商管理",
        "key_words": [
            "总则",
            "建立完善招标投标工作监督机制",
            "指导协调招标投标工作",
            "检查行政监察对象"
        ],
        "label": [
            {
                "clause_id": 341,
                "content": "国务院发展改革部门指导和协调全国招标投标工作，对国家重大建设项目的工程招标投标活动实施监督检查。国务院工业和信息化、住房城乡建设、交通运输、铁道、水利、商务等部门，按照规定的职责分工对有关招标投标活动实施监督。县级以上地方人民政府发展改革部门指导和协调本行政区域的招标投标工作。县级以上地方人民政府有关部门按照规定的职责分工，对招标投标活动实施监督，依法查处招标投标活动中的违法行为。县级以上地方人民政府对其所属部门有关招标投标活动的监督职责分工另有规定的，从其规定。财政部门依法对实行招标投标的政府采购工程建设项目的政府采购政策执行情况实施监督。监察机关依法对与招标投标活动有关的监察对象实施监察。"
            }
        ],
    }
### Candidate
{
        "clause_id": 2948,
        "clause_content": "为了有效预防和扑救森林火灾，保障人民生命财产安全，保护森林资源，维护生态安全，根据《中华人民共和国森林法》，制定本条例。",
        "keywords": [
            "总则",
            "立法目的"
        ],
        "title": "森林防火条例",
        "regulations_id": 0,
        "category": "林业"
    },

### Label
{
        "q_id": 14675,
        "label_ids": [
            14947,
            14988
        ]
    }


**`Here are the explanations of the fields.`**

```json
{
"query_id": "the query article's unique ID",
"clause_content": "the content of the query article",
"regulations_id": "the regulation ID to which the query article belongs",
"title": "the title of the regulation",
"superior_law_regulations_id": "the superior regulations ID to which query article belongs",
"category": "the category of the query article",
"key_words": "the key words of the query article",
"label": {
    "clause_id": "the superior legal articles ID of the query article",
    "content": "the content of the superior legal articles"
},
"q_id": "the query article's ID",
"label_ids": "label of superior legal articles' ID of query article"
}
``` 

### Data Statistic
SLARD contains 2,627 query articles and 9,183 candidate articles.
markdown table
| Dataset           | SLARD           |
|-------------------|-----------------|
| # Query Articles   | 2,627           |
| # Candidate Articles | 9,183          |
| average length of query articles | 127 |  
| average length of candidate articles | 119 | 

## Experiment
We use Milvus as the embedding vector search engine
For BM25, we use [ElasticSearch](https://www.elastic.co/cn/elasticsearch) to implement the retrieval model.

other retrieval models' implement can be found via the following links:
[uniem](https://github.com/wangyuxinwhy/uniem), [DPR](https://github.com/facebookresearch/DPR), [RetroMAE](https://github.com/staoxiao/RetroMAE), [ColBERT](https://github.com/IBM/ColBERT-practical)

