# Fine-Tuning and Evaluation of a Small Language Model for English–Hindi Translation

## Overview
This project focuses on fine-tuning and evaluating a **Small Language Model (SLM)** for **English–Hindi machine translation**. A pretrained **IndicTrans2 (200M parameters)** model was fine-tuned using the **IIT Bombay English–Hindi dataset** and evaluated using automatic metrics, decoding experiments, and human evaluation.

The objective of this assignment is to demonstrate effective fine-tuning, systematic evaluation, and proper documentation of a bilingual SLM within limited computational resources.

---

## Model Used
- **Model:** ai4bharat/indictrans2-en-indic-dist-200M  
- **Architecture:** Transformer-based encoder–decoder  
- **Parameter Size:** ~200M  
- **Languages:** English ↔ Hindi  

IndicTrans2 requires explicit source and target language tags and is designed for high-quality translation across Indian languages.

---

## Approach
<img width="390" height="829" alt="image" src="https://github.com/user-attachments/assets/58824909-a9a6-4157-9ad8-009b34b3a47a" />

A **fine-tuning approach** was adopted instead of training a model from scratch. This allows leveraging the pretrained multilingual knowledge of IndicTrans2 while adapting it specifically for the English–Hindi translation task.

Fine-tuning was performed using the Hugging Face Transformers framework with early stopping to prevent overfitting.

---

## Dataset
- **Dataset:** IIT Bombay English–Hindi Parallel Corpus  
- **Usage:** Training, validation, and test splits  
- **Type:** Parallel sentence pairs  

The IIT Bombay dataset is a widely used benchmark for English–Hindi machine translation and ensures reliable evaluation.
Dataset Link - https://huggingface.co/datasets/cfilt/iitb-english-hindi

---

## Compute Resources
- **Platform:** Kaggle  
- **GPU:** NVIDIA P100  

The available GPU resources were sufficient to fine-tune the model and perform decoding and evaluation experiments.

---

## Training Setup
- Optimizer: AdamW  
- Learning Rate: 1e-5  
- Epochs: Up to 10  
- Dropout: 0.1  
- Early Stopping: Enabled  

Training was performed using gradient accumulation to manage memory constraints.

---

## Evaluation Methodology
Model evaluation was conducted using a combination of automatic metrics, decoding analysis, and human evaluation.

### Automatic Metrics
- **BLEU**
- **ROUGE-1**
- **ROUGE-2**
- **ROUGE-L**

Fine-tuning resulted in consistent improvements across BLEU and ROUGE metrics compared to the baseline model.

### Decoding Experiments
The model was tested using different decoding strategies:
- Beam Search (baseline)
- Sampling with different **temperature**, **top-k**, and **top-p** values

These experiments highlighted the impact of decoding parameters on translation quality and diversity.

### Human Evaluation
Human evaluation was conducted on **50 test samples** using the following criteria:
- Adequacy
- Fluency
- Overall Quality  

Each criterion was rated on a 5-point scale, confirming that the model produces accurate and fluent translations.

---

## Results Summary

| Metric   | Baseline Model | Fine-Tuned Model | Improvement |
|--------|----------------|------------------|-------------|
| BLEU   | 21.83          | 22.72            | +0.89       |
| ROUGE-1 | 0.1645        | 0.1667           | +0.0022    |
| ROUGE-2 | 0.0452        | 0.0525           | +0.0073    |
| ROUGE-L | 0.1608        | 0.1620           | +0.0012    |

All metrics were computed on the IIT Bombay English–Hindi test set.

---

## Instruction Following and Context Awareness
The model demonstrates strong instruction-following by consistently translating English inputs into Hindi without hallucination or language switching. Context awareness was validated through stable translations of long and multi-clause sentences, preserving semantic continuity without repetition or truncation.
<img width="625" height="203" alt="image" src="https://github.com/user-attachments/assets/07515bdd-98c6-469a-a120-f50cc00b8eac" />
<img width="682" height="302" alt="image" src="https://github.com/user-attachments/assets/c823f745-5519-42e0-8c93-3846e0c9eaeb" />

---

## Model Access
The fine-tuned model can be accessed at:  
**[https://huggingface.co/deepanshumiglani0408/indictrans2_finetune]**

---

## Conclusion and Future Work
The fine-tuned IndicTrans2 model shows improved translation quality for English–Hindi tasks. Future work may include:
- Training on larger and more diverse datasets  
- Applying back-translation and multi-task learning  
- Extending support to additional Indian language pairs  
- Deploying the model as a production-ready API  
- Conducting broader human evaluation across domains  

---

## Author
**Deepanshu Miglani**
