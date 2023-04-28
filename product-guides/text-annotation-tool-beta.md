---
description: Multiple rounds of dialogues
---

# 📖 Text Annotation Tool (beta)

{% hint style="info" %}
Multiple rounds of dialogues annotation refer to the process of annotating a conversation between two or more parties through multiple iterations or rounds of annotation. In this process, after annotating each round of dialogue, the annotations are reviewed and corrected if necessary before proceeding to the next round of annotation. This iterative process is often used when handling complex or nuanced conversations that require careful analysis and interpretation.&#x20;

Multiple rounds of dialogue annotation can help ensure data quality and accuracy by allowing annotators to review their work and make corrections before moving on to subsequent rounds. It also helps to improve inter-annotator agreement and reduces errors and inconsistencies in the final annotated dataset.
{% endhint %}

## Features

#### Data Upload

Users can proactively upload multiway tree structured dialogue text data (JSON). Xtreme1 supports processing of complex dialogue structures and splits each leaf node to root node path into individual data for subsequent annotation work.

#### Custom Annotation Options

Xtreme1 provides functionality to establish required classification options from the dataset's ontology, allowing users to customize annotation options according to actual needs. For example, users can create classification tags such as "quality rating," "humor level," and "helpfulness" for text data, facilitating more detailed evaluation and analysis of data.

#### Like / Dislike

To allow users to intuitively evaluate text data, Xtreme1 provides the ability to label text as 'like' or 'dislike,' collecting user preference information and providing useful reference for future model training.

<figure><img src="../.gitbook/assets/0.7.png" alt=""><figcaption></figcaption></figure>

#### Long Text Input

With the "long text" feature, users can input replies to form new data. This allows users to provide more detailed information and helps to increase the diversity of the dataset. By collecting replies of different types, the generalization ability of the model can be improved.

#### Data Flow

Xtreme1 supports selection and filtering of data status (valid / invalid) and annotation status (annotated / unannotated / invalid), making it easier to manage and process data and ensuring data quality and completeness.

#### Dataset Splitting

For text-type datasets, Xtreme1 also supports dataset splitting. Users can divide the dataset into training, validation, and testing sets for model training, validation, and final evaluation. This helps to improve the performance of the model, thus achieving more accurate predictions and recommendations.

## Sample dataset

```
LLM text annotation dataset structure
├── test
│   ├── 00.json
```

A sample dataset can be [download at here](https://app.box.com/s/v97k7rlrs8oxhz12iz3f3qcgr3p5vukc).
