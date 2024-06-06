# Answering the Unanswered: Overcoming Language Barriers in Question Answering
Overcoming language barriers in question answering by evaluating and enhancing multilingual models for low-resource languages.

This repository contains the project code and documentation for "Overcoming Language Barriers in Question Answering," a research effort aimed at improving the performance of multilingual question-answering systems, especially for low-resource languages.

## Table of Contents
- [Introduction](#introduction)
- [Related Work](#related-work)
- [Methodology](#methodology)
- [Datasets](#datasets)
- [Results](#results)
- [Future Work](#future-work)
- [Contributors](#contributors)

## Introduction
In recent years, significant progress has been made in Natural Language Processing (NLP) tasks like question answering, thanks to advancements in large language models such as GPT-4. However, these models perform well primarily on high-resource languages like English and Chinese. For many regional languages, there is a lack of data and benchmarks, resulting in subpar performance on NLP tasks. This project seeks to bridge this gap by extending existing work in the question-answering domain to include more low-resource languages.

## Related Work
- **mBERT**: Multilingual BERT uses Wikipedia pages from 104 languages for pre-training and has shown deeper multilingual representation capabilities beyond simple vocabulary memorization.
- **XLM-RoBERTa**: This model builds on mBERT's architecture with enhanced training on a larger dataset, providing superior performance on low-resource languages through representation learning.

## Methodology
Our approach involves three main steps:
1. **Data Augmentation**: We expand the TyDi QA dataset with additional question-answer pairs from various sources, including Hindi, Tamil, and Persian datasets.
2. **Model Fine-Tuning**: We fine-tune an ensemble of XLM-RoBERTa models, each tailored to specific language categories.
3. **Evaluation**: We evaluate the models on augmented and untranslated datasets to ensure robust performance across languages.

## Datasets
We utilize multiple datasets, including:
- **TyDi QA**: A diverse dataset with question-answer pairs from 11 typologically varied languages.
- **SQuAD**: An English dataset for question answering that aids in modeling question-answer paradigms.
- **chaii**: A dataset containing question-answer pairs in Hindi and Tamil.
- **PQuAD**: A dataset with Persian question-answer pairs.


## Results
Our experiments show significant improvements over baseline models, particularly for low-resource languages. Detailed results are available in the `results/` directory, showcasing performance metrics such as F1 scores, precision, and recall for each language.

## Future Work
We plan to explore fine-tuning large language models like GPT-4 for multilingual question answering using few-shot prompt engineering to further enhance performance.

## Contributors
- **Archit Bansal** - ab2465@rutgers.edu
- **Shreesh Keskar** - skk139@rutgers.edu
- **Saransh Sharma** - ss4368@rutgers.edu
- **Devarata Oza** - do309@rutgers.edu
---

Feel free to modify the content as per your project's specifics and update any placeholder links or contact information.
