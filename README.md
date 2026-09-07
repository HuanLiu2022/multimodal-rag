# Multimodal RAG for Historical Artifacts

## Overview

This project explores multimodal approaches for generating metadata and descriptions of historical artifacts using artifact images, textual knowledge, multimodal models, and retrieval-augmented generation.

## Objectives

- Generate structured metadata from historical artifact images
- Generate detailed artifact descriptions
- Combine visual and textual information using RAG
- Fine-tune multimodal and language models
- Evaluate model performance

## Datasets

The project uses two historical artifact collections:

- **Archäologische Sammlung UZH** – German-language artifact collection
- **The Metropolitan Museum of Art (The Met)** – English-language artifact collection

The final UZH dataset contains 495 artifacts and 4,675 images. 
The final MET dataset contains 5,727 artifacts and 8,428 images. 

## Project Pipeline

```text
Artifact Data
     │
     ▼
Data Preparation
     │
     ▼
Model Fine-tuning
     │
     ▼
RAG & Knowledge Retrieval
     │
     ▼
Metadata & Description Generation
     │
     ▼
Evaluation
```

## Models & Methods

The project experiments with:

- BLIP2-Flan-T5-XL
- GPT-4o
- CLIP
- LoRA fine-tuning
- Retrieval-Augmented Generation (RAG)
- FAISS
- Sentence Transformers
- OpenAI Embeddings

### RAG

The RAG pipeline retrieves relevant information from external historical literature and combines it with artifact images and prompts for multimodal generation.

CLIP (ViT-B/32) was initially explored for multimodal retrieval. However, its **77-token text context length** limited the retrieval of longer bibliographic texts. Therefore, the main RAG pipeline used **OpenAI `text-embedding-3-large`** for text retrieval instead.

## Fine-tuning

**BLIP2-Flan-T5-XL** was fine-tuned using LoRA, with the vision encoder and Q-Former frozen.

**GPT-4o** was also fine-tuned using the OpenAI API. The workflow included preparing JSONL training data, creating a fine-tuning job, running inference, and evaluating the results.

## Evaluation

The project uses:

- Accuracy
- Precision
- Recall
- F1-score
- METEOR
- ROUGE
- BERTScore

Selected experiments achieved **90%+ classification accuracy** and **BERTScores of up to approximately 0.84**.

## Repository Structure

```text
```text
multimodal-rag/
├── README.md
└── notebooks/
    ├── data_preparation.ipynb
    ├── RAG.ipynb
    └── fine_tuning_and_evaluation/
        ├── BLIP2-Flan-T5-XL_Multitask_MET.ipynb
        ├── BLIP2-Flan-T5-XL_Multitask_UZH.ipynb
        ├── GPT-4o_Classifier_MET.ipynb
        ├── GPT-4o_Classifier_UZH.ipynb
        ├── GPT-4o_Describer_MET.ipynb
        └── GPT-4o_Describer_UZH.ipynb
```

## Technologies

**Programming:** Python, PyTorch, Hugging Face Transformers

**Models:** CLIP, BLIP, BLIP2-Flan-T5-xl, GPT-4o

**RAG & Retrieval:** FAISS, Sentence Transformers, OpenAI Embeddings, LangChain

**Fine-tuning:** LoRA, OpenAI Fine-tuning API

**Environment:** Google Colab, NVIDIA A100-SXM4-40GB
