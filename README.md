# Multimodal RAG for Historical Artifacts

**Master's Thesis · University of Zurich**

## Overview

This project explores multimodal RAG-based approaches for generating metadata and descriptions of historical artifacts using vision-language models and large language models.

The goal is to combine visual information, existing artifact metadata, and external knowledge to generate informative and context-aware descriptions.

## Approach

The project combines several components:

- **Vision-Language Models** for understanding historical artifact images
- **Large Language Models** for metadata and description generation
- **Retrieval-Augmented Generation (RAG)** for incorporating relevant external knowledge
- **Embedding-based Retrieval** for finding relevant information from a knowledge base
- **Model Fine-tuning** to adapt models to the target domain
- **Automated Evaluation** using classification and text-generation metrics

## Models & Technologies

- Python
- PyTorch
- Hugging Face Transformers
- BLIP
- BLIP-2
- Flan-T5
- GPT-4o
- LoRA
- LangChain
- FAISS
- Sentence Transformers
- OpenAI Embeddings

## Datasets

The project uses historical artifact collections from two sources:

- **University of Zurich (UZH)** — German-language historical artifact data
- **The Metropolitan Museum of Art (The Met)** — English-language artifact data

The datasets contain artifact images and associated metadata used for model training, retrieval, and evaluation.

## Pipeline

The overall workflow consists of the following stages:

```text
     Artifact Images
            │
            ▼
     Data Preparation
            │
            ▼
   Knowledge Retrieval
  (Embeddings + FAISS)
            │
            ▼
   Multimodal Generation
(BLIP2-Flan-t5-xl / GPT-4o)
            │
            ▼
 Metadata & Description
        Generation
            │
            ▼
        Evaluation ```

## Model Training

BLIP-2 with Flan-T5 was fine-tuned using **LoRA**, while the vision encoder and Q-Former were kept frozen.

The project also explored GPT-4o-based approaches for multimodal generation and evaluated the generated descriptions against reference data.

## Evaluation

Model performance was evaluated using both classification and text-generation metrics, including:

- Accuracy
- METEOR
- ROUGE
- BERTScore

## Evaluation Results

The experiments achieved classification accuracy above **90%**, with BERTScore values of up to approximately **0.84**, depending on the dataset and model configuration.

The results demonstrate the potential of multimodal and retrieval-augmented approaches for generating metadata and descriptions of historical artifacts.

## Project Structure

```text
multimodal-rag/
│
├── notebooks/
├── results/
├── README.md
└── requirements.txt
```
