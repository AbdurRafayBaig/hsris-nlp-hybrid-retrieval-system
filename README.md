<<<<<<< HEAD
# Assignment 3: Hybrid Semantic Retrieval & Intelligence System (HSRIS)

## Overview
This repository contains the complete solution for Assignment 3. The project implements a multi-stage Natural Language Processing (NLP) pipeline for processing customer support tickets.

Our search engine uses a hybrid approach:
- **TF-IDF (Term Frequency-Inverse Document Frequency):** To match exact keywords in the tickets.
- **GloVe (300D):** Pre-trained sentence embeddings to understand semantic meaning (e.g. matching "refund" with "billing").

The final score is a weighted combination of both metrics:
`FinalScore = α(TF-IDF) + (1-α)(GloVe)`

## Technical Requirements
The entire pipeline was built under strict base computational constraints:
- Built strictly with base PyTorch and NumPy (No Scikit-Learn TfidfVectorizer or LabelEncoder).
- Employs **Dual T4 GPU** parallel execution for optimized similarity search logging.
- Uses `torch.sparse` matrices to fit heavy TF-IDF encodings into memory.
- Implements custom `[UNK]` token routing to handle Out-Of-Vocabulary (OOV) tokens dynamically.
- Interactive Gradio interface for demonstration.

## Structure
- `DS_ASS01_XXF_YYYY.ipynb`: The main Kaggle-ready notebook containing all steps, including preprocessing, custom TF-IDF generation, GloVe embeddings, similarity measurements, and the UI.
- `Medium_Article.md`: An explanatory technical article diving into the rationale behind hybrid engines and sparse computational techniques.
- `Report.md`: A summary and portal to all assignment links as required by the grading prompt.
- `LinkedIn_Post.txt`: Promotional post material showing off the completed search capabilities.

## Execution Requirements
1. The `.ipynb` file should be run exclusively on Kagan with **GPU T4 x2 (Dual GPU)** enabled.
2. The user must manually attach the `GloVe 6B 300d` dataset via Kaggle `+ Add Input` prior to running the notebook.
3. The original Customer Ticket dataset must also be accessible via Kaggle at `../input/customer-support-ticket-dataset/`.

## Results Summary
- **Precision@5:** Exceeded benchmark semantic grouping precision on un-structured queries. 
- **Time/Batch Curve:** Using `torch.nn.DataParallel` significantly cut latency during batch scaling arrays > 64 instances.
=======
# hsris-nlp-hybrid-retrieval-system
Hybrid Semantic Retrieval &amp; Intelligence System (HSRIS) built with PyTorch, combining TF-IDF keyword search and GloVe-based semantic embeddings for intelligent customer support ticket retrieval.
>>>>>>> e8fe1b2ce91928fa48f43aa75bd12076b8c8ab73
