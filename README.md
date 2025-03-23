# DragonVerseQA

## Overview

DragonVerseQA is a context-aware question-answering dataset specifically designed for Game of Thrones and House of the Dragon. It contains structured QA pairs derived from episode summaries, user reviews, and character interactions, making it ideal for natural language processing (NLP) tasks involving narrative-based QA generation.

##Dataset Structure

The dataset is stored in JSON format and consists of multiple QA pairs, each with a structured format including the context, generated question, and corresponding answer.follows the structure below:

JSON Structure

Each entry in DragonVerseQA.json follows this format:

{
  "context": "Daemon Targaryen claims Dragonstone without the King's consent.",
  "question": "What led Daemon Targaryen to seize Dragonstone?",
  "answer": "Daemon believed he was the rightful heir after Viserys' decision to name Rhaenyra as his successor."
": {
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

## Fields Explanation

context: A passage extracted from episode summaries, user reviews, or script dialogues.

question: The automatically or manually generated question related to the context.

answer: A reference answer validated by domain experts and NLP techniques.

Dataset Statistics

Dataset Split

Number of QA Pairs

Training Set

2500

Validation Set

500

Test Set

200

Total

3200

Data Sources

Episode Summaries (HBO & official Game of Thrones materials)

Fan-written recaps and analyses

Script dialogues from episodes

User reviews (IMDb, Rotten Tomatoes)

Fantasy wikis and lore-based knowledge graphs

Dataset Statistics

Dataset Split

Number of QA Pairs

Training Set

2500

Validation Set

500

Test Set

200

Usage Guidelines

Recommended Use Cases

Fine-tuning QA models (e.g., BERT, T5, GPT) for narrative-driven question answering.

Evaluating multi-hop reasoning capabilities in NLP models.

Developing interpretive and opinion-based QA models using user sentiment.

How to Load the Dataset in Python

import json

with open("DragonVerseQA.json", "r", encoding="utf-8") as file:
    dataset = json.load(file)

## Example - Print first QA pair

print("Episode:", dataset[0]["context"]["episode"])
print("Summary:", dataset[0]["context"]["summary"])
print("Characters:", dataset[0]["context"]["characters"])
print("Review Source:", dataset[0]["context"]["reviews"][0]["source"])
print("Review:", dataset[0]["context"]["reviews"][0]["review"])
print("Question:", dataset[0]["qa_pairs"][0]["question"])
print("Answer:", dataset[0]["qa_pairs"][0]["answer"])

Evaluation Metrics

To assess QA model performance on DragonVerseQA, the following metrics can be used:

BLEU Score (lexical similarity)

ROUGE-L Score (recall-oriented phrase matching)

Semantic Similarity (BERTScore) (meaning preservation)

Human Evaluation (fluency, coherence, and accuracy ratings)

License & Citation

License: [Specify License Here]

Citation Format:

@article{DragonVerseQA,
  author = {Your Name},
  title = {DragonVerseQA: A Domain-Specific QA Dataset for Fantasy Narratives},
  year = {2024},
  journal = {Game of Thrones NLP Research}
}

Contributing & Contact

For contributions or inquiries, please reach out to:

[Your Email]

GitHub Repository [if applicable]

