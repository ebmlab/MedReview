# MedReview

This repository contains the datasets, scripts, and models associated with the paper:

**Title**: [Closing the gap between open source and commercial large language models for medical evidence summarization](https://www.nature.com/articles/s41746-024-01239-w)  
**Authors**: Gongbo Zhang, Qiao Jin, Yiliang Zhou, Song Wang, Betina Idnay, Yiming Luo, Elizabeth Park, Jordan G. Nestor, Matthew E. Spotnitz, Ali Soroush, Thomas R. Campion Jr., Zhiyong Lu, Chunhua Weng* & Yifan Peng* 
**Published in**: *npj Digital Medicine*  
**Year**: 2024  
**DOI**: [(https://doi.org/10.1038/s41746-024-01239-w)]([DOI_LINK](https://doi.org/10.1038/s41746-024-01239-w))

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Citation](#citation)
- [License](#license)

## Introduction

This repository provides the data and code used in the paper *Closing the gap between open source and commercial large language models for medical evidence summarization*, published in *npj Digital Medicine*. The paper explores how fine-tuning open-source large language models (LLMs) such as **PRIMERA**, **LongT5**, and **Llama-2** can improve their performance in summarizing medical evidence, as compared to proprietary models like GPT-3.5 and GPT-4.

Summarizing medical evidence is a critical task in healthcare research, and large language models have shown great potential in automating this process. However, most recent studies focus on proprietary LLMs, which introduce issues such as lack of transparency and vendor lock-in. Open-source LLMs, while offering more transparency and flexibility, typically underperform when compared to their proprietary counterparts.

In this study, we fine-tune three widely-used, open-source LLMs—**PRIMERA**, **LongT5**, and **Llama-2**—using the **MedReview** dataset, which contains 8161 pairs of systematic reviews and summaries. Our results show that fine-tuning these models improves their performance, with **LongT5** reaching a performance level comparable to GPT-3.5 under zero-shot conditions. In some cases, smaller fine-tuned models even outperform larger zero-shot models.

The performance improvements were confirmed through both human evaluations and large-scale GPT-4-simulated evaluations.

## Dataset

The **MedReview** dataset, used in this study, is a benchmark dataset designed for evaluating large language models on the task of summarizing medical evidence. It consists of **8161 pairs** of systematic reviews and corresponding summaries.

### Dataset Details

- **Data Type**: Text
- **Number of Pairs**: 8161 pairs of systematic reviews and summaries
- **Annotations**: Each systematic review is paired with an expert-written summary
- **File Formats**: JSON
- **Source**: Curated from publicly available systematic review repositories
- **Use Case**: The dataset is used for training, validating, and testing large language models on summarizing medical evidence. Each pair provides a systematic review with its condensed version, serving as the ground truth for the models.

### Files

| Filename                  | Description                                                     |
|---------------------------|-----------------------------------------------------------------|
| `train.json` | Training data: systematic reviews and summaries for model training |
| `val.json`       | Validation data: used during training to tune hyperparameters    |
| `test_before_cutoff.json`       | Test data: used to evaluate the model's performance (before 09/22)    |
| `test_after_cutoff.json`      | Test data: used to evaluate the model's performance (after 09/22)        |


### Structure

Each line is a JSON object that contains the following fields:
- **doi**: The doi of the systematic review
- **abstract**: A complete abstract of the systematic review
- **conclusion**: A concise summary of the structed abstract, written by paper authors

The dataset is split into training, validation, and test sets for model development, tuning, and evaluation.

## Citation

If you use the dataset, models, or code from this repository in your research, please cite the following paper:


You can also use the following BibTeX entry for citation:

```bibtex
@article{DBLP:journals/npjdm/ZhangJZWILPNSSCLWP24,
  author       = {Gongbo Zhang and
                  Qiao Jin and
                  Yiliang Zhou and
                  Song Wang and
                  Betina Idnay and
                  Yiming Luo and
                  Elizabeth Park and
                  Jordan G. Nestor and
                  Matthew E. Spotnitz and
                  Ali Soroush and
                  Thomas Campion and
                  Zhiyong Lu and
                  Chunhua Weng and
                  Yifan Peng},
  title        = {Closing the gap between open source and commercial large language
                  models for medical evidence summarization},
  journal      = {npj Digit. Medicine},
  volume       = {7},
  number       = {1},
  year         = {2024},
  url          = {https://doi.org/10.1038/s41746-024-01239-w},
  doi          = {10.1038/S41746-024-01239-W},
  timestamp    = {Fri, 20 Sep 2024 14:02:35 +0200},
  biburl       = {https://dblp.org/rec/journals/npjdm/ZhangJZWILPNSSCLWP24.bib},
  bibsource    = {dblp computer science bibliography, https://dblp.org}
}
```

## License

This repository is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
