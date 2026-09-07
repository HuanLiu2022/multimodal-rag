# Fine-tuning & Evaluation

This folder contains the notebooks used for model fine-tuning and evaluation.

| Notebook | Description |
|---|---|
| `BLIP2-Flan-T5-XL_Multitask_MET.ipynb` | Fine-tunes BLIP2-Flan-T5-XL with LoRA on The Met dataset for English-language metadata and description generation, followed by classification and text-generation evaluation. |
| `BLIP2-Flan-T5-XL_Multitask_UZH.ipynb` | Fine-tunes BLIP2-Flan-T5-XL with LoRA on the UZH dataset for German-language metadata and description generation, with classification and text-generation evaluation. |
| `GPT-4o_Classifier_MET.ipynb` | Fine-tunes GPT-4o on The Met dataset for structured artifact metadata classification and compares its performance with zero-shot and few-shot GPT-4o.|
| `GPT-4o_Classifier_UZH.ipynb` | Fine-tunes GPT-4o on the UZH dataset for structured artifact metadata classification and evaluates the results using accuracy, precision, recall, and F1-score. |
| `GPT-4o_Describer_MET.ipynb` | Fine-tunes GPT-4o on The Met artifact images and descriptions for description generation and evaluates the generated descriptions using BLEU, ROUGE, METEOR, and BERTScore. |
| `GPT-4o_Describer_UZH.ipynb` | Fine-tunes GPT-4o on The UZH artifact images and descriptions for description generation and evaluates the generated descriptions using BLEU, ROUGE, METEOR, and BERTScore. |
