# English-to-Hindi Neural Machine Translation

**Course:** ICT4403 – Foundations of Generative AI  
**Assignment:** 3  
**Student:** Adarsh Agrawal  
**Registration Number:** 230911264  
**Institution:** Manipal Institute of Technology, MAHE

## Problem Statement

This project implements and compares four neural machine translation approaches for English-to-Hindi translation using a parallel-text dataset.

## Objectives

- Implement a basic Transformer encoder–decoder from scratch.
- Fine-tune the multilingual mT5-small model.
- Evaluate LLaMA 3.2 1B and Gemma 2 2B using zero-shot translation prompting.
- Compare translation quality, inference time and model parameters.

## Dataset

**Hindi-English Parallel Corpus**

Source: https://www.kaggle.com/datasets/vaibhavkumar11/hindi-english-parallel-corpus

A cleaned sample of 12,000 parallel sentence pairs was used.

| Partition | Pairs |
|---|---:|
| Training | 10,000 |
| Validation | 1,000 |
| Testing | 1,000 |
| Final evaluation subset | 200 |

The mT5 repair experiment used a smaller training subset of 1,000 pairs.

## Models

1. Basic Transformer – Encoder–decoder architecture.
2. mT5-small – Multilingual encoder–decoder, fine-tuned.
3. LLaMA 3.2 1B Instruct – Decoder-only, zero-shot prompting.
4. Gemma 2 2B IT – Decoder-only, zero-shot prompting.

## Evaluation Results

| Model | BLEU | chrF | Average inference (s) |
|---|---:|---:|---:|
| Basic Transformer | 0.0879 | 3.6094 | 0.2443 |
| mT5-small | 0.0168 | 0.0729 | 0.0770 |
| LLaMA 3.2 1B | 4.0284 | 23.4057 | 0.7901 |
| Gemma 2 2B | 8.7222 | 31.8949 | 1.4182 |

## Observations

Gemma 2 2B achieved the highest BLEU and chrF scores, followed by LLaMA 3.2 1B.

The Basic Transformer and mT5-small produced weak translations in the current experiments. Qualitative inspection showed repetitive output from the Basic Transformer and sentinel-token output from mT5.

The decoder-only models were evaluated using zero-shot prompting and were not fine-tuned on the translation dataset.

## Computational Environment

- Kaggle Notebook
- NVIDIA Tesla T4 GPU
- Python
- PyTorch
- Hugging Face Transformers
- SentencePiece
- SacreBLEU

## Execution

1. Open the notebook in Kaggle.
2. Attach the Hindi-English Parallel Corpus dataset.
3. Enable GPU acceleration.
4. Configure the required Hugging Face access token for gated models.
5. Execute the notebook cells sequentially.

## Limitations

- Final metric evaluation used 200 examples.
- Training budgets differed across models.
- LLaMA and Gemma were evaluated zero-shot.
- Basic Transformer and mT5 results indicate unsuccessful translation learning in the current runs.
- Dataset noise and alignment quality may affect evaluation.
- No sampling-temperature sweep was recorded.

## Conclusion

Gemma 2 2B achieved the best observed translation performance in this experiment. However, the comparison is preliminary because model sizes, training budgets and adaptation methods differed.

## Repository Contents

- `notebooks/` – Kaggle notebook implementation.
- `results/` – Evaluation tables, generated translations, metadata and plots.
- `report/` – Final assignment report.

## Responsible AI

Translation outputs can contain bias, hallucinations, cultural misrepresentation and meaning drift. Human verification is recommended, especially for sensitive medical, legal and financial content.
