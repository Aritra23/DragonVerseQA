# **DragonVerseQA Dataset**

## **Overview**
DragonVerseQA is a **context-aware question-answering dataset** specifically designed for **Game of Thrones** and **House of the Dragon**. It contains structured QA pairs derived from **episode summaries, user reviews, and character interactions**, making it ideal for **natural language processing (NLP) tasks involving narrative-based QA generation**.

## **Dataset Structure**
The dataset is stored in **JSON format** and follows the structure below:

```json
{
  "context": {
    "episode": "Episode Name",
    "summary": "Episode summary",
    "characters": "Primary Characters",
    "reviews": [
      {
        "source": "IMDB/RottenTomatoes",
        "review": "Top-k Filtered reviews"
      }
    ]
  },
  "qa_pairs": [
    {
      "question": "Questions on episode plot",
      "answer": "Long-form supporting Answer"
    }
  ]
}
```

### **Fields Explanation**
- **context**: Metadata about the episode, including:
  - **episode**: The title of the episode.
  - **summary**: A condensed version of the episode’s main plot.
  - **characters**: The primary characters involved in the episode.
  - **reviews**: Audience/user opinions sourced from IMDb and Rotten Tomatoes, filtered for relevance.
- **qa_pairs**: A collection of **question-answer pairs** related to the episode plot.
  - **question**: A question generated based on the episode’s content.
  - **answer**: A long-form answer supported by the episode’s summary and reviews.

## **Dataset Statistics**
| **Dataset Split** | **Number of QA Pairs** |
|------------------|------------------|
| Training Set | 2500 |
| Validation Set | 500 |
| Test Set | 200 |
| **Total** | **3200** |

## **Data Sources**
- **Episode Summaries** (HBO & official Game of Thrones materials)
- **Fan-written recaps and analyses**
- **Script dialogues from episodes**
- **User reviews (IMDb, Rotten Tomatoes)**
- **Fantasy wikis and lore-based knowledge graphs**

## **Usage Guidelines**
### **Recommended Use Cases**
- **Fine-tuning QA models (e.g., BERT, T5, GPT)** for **narrative-driven question answering**.
- **Evaluating multi-hop reasoning capabilities** in NLP models.
- **Developing interpretive and opinion-based QA models** using user sentiment.

### **How to Load the Dataset in Python**
```python
import json

with open("DragonVerseQA.json", "r", encoding="utf-8") as file:
    dataset = json.load(file)

# Example - Print first episode context and QA pair
print("Episode:", dataset[0]["context"]["episode"])
print("Summary:", dataset[0]["context"]["summary"])
print("Characters:", dataset[0]["context"]["characters"])
print("Review Source:", dataset[0]["context"]["reviews"][0]["source"])
print("Review:", dataset[0]["context"]["reviews"][0]["review"])
print("Question:", dataset[0]["qa_pairs"][0]["question"])
print("Answer:", dataset[0]["qa_pairs"][0]["answer"])
```

## **Evaluation Metrics**
To assess QA model performance on DragonVerseQA, the following metrics can be used:
- **BLEU Score** (lexical similarity)
- **ROUGE-L Score** (recall-oriented phrase matching)
- **Semantic Similarity (BERTScore)** (meaning preservation)
- **Human Evaluation (fluency, coherence, and accuracy ratings)**

## **License & Citation**
- **License**: [Specify License Here]
- **Citation Format**:
```bibtex
@article{lahiri2024dragonverseqaopendomainlongformcontextaware,
      title={DragonVerseQA: Open-Domain Long-Form Context-Aware Question-Answering}, 
      author={Aritra Kumar Lahiri and Qinmin Vivian Hu},
      year={2024},
      eprint={2412.16694},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2412.16694}, 
}
```

## **Contributing & Contact**
For contributions or inquiries, please reach out to:
- **aritra.lahiri@torontomu.ca**
