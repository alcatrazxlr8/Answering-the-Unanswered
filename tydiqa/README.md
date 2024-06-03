# Answering the Unanswered: Overcoming Language Barriers in Question Answering

This repository contains information about TyDi QA, code for evaluating results
on the dataset, implementations of baseline systems for the dataset, and some
advice for working with the dataset.

# Introduction

TyDi QA is a question answering dataset covering 11 typologically diverse
languages with 204K question-answer pairs. The languages of TyDi QA are diverse
with regard to their typology -- the set of linguistic features that each
language expresses -- such that we expect models performing well on this set to
generalize across a large number of the languages in the world. It contains
language phenomena that would not be found in English-only corpora. To provide a
realistic information-seeking task and avoid priming effects, questions are
written by people who want to know the answer, but don’t know the answer yet,
(unlike SQuAD and its descendents) and the data is collected directly in each
language without the use of translation (unlike MLQA and XQuAD).

# The Tasks

*   Primary tasks:
    *   **Passage selection task (SelectP):** Given a list of the passages in
        the article, return either (a) the index of the passage that answers the
        question or (b) NULL if no such passage exists.
    *   **Minimal answer span task (MinSpan):** Given the full text of an
        article, return one of (a) the start and end byte indices of the minimal
        span that completely answers the question; (b) YES or NO if the question
        requires a yes/no answer and we can draw a conclusion from the passage;
        (c) NULL if it is not possible to produce a minimal answer for this
        question.
*   Secondary task:
    *   **Gold passage task (GoldP):** Given a passage that is guaranteed to
        contain the answer, predict the single contiguous span of characters
        that answers the question. This is more similar to existing reading
        comprehension datasets (as opposed to the information-seeking task
        outlined above). This task is constructed with two goals in mind: (1)
        more directly comparing with prior work and (2) providing a simplified
        way for researchers to use TyDi QA by providing compatibility with
        existing code for SQuAD 1.1, XQuAD, and MLQA. Toward these goals, the
        gold passage task differs from the primary task in several ways:
        *   only the gold answer passage is provided rather than the entire
            Wikipedia article;
        *   unanswerable questions have been discarded, similar to MLQA and
            XQuAD;
        *   we evaluate with the SQuAD 1.1 metrics like XQuAD; and
        *   Thai and Japanese are removed since the lack of whitespace breaks
            some tools.

# Incremental Changes over Baseline

For this project, we have attempted to improve on the baseline results for the 
**Minimal answer span task (MinSpan)** task. To do this, we have used the XLM-Roberta 
pretrained model available on HuggingFace and fine-tuned it using the TyDiQA data
augmented with additional data and languages as described in the report.

Since XLM-RoBERTa has the same model architecture as BERT, the model weights can be
loaded directly to the existing architecture (in the TyDiQA baseline code) with minimal
changes.

To run the code, please follow the instructions in the baseline folder.
