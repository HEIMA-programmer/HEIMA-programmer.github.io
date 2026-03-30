---
layout: post
title: "Contrastive learning in bioinformatics: a reading note"
tags: [paper-reading, contrastive-learning]
---

Read a few papers on contrastive learning for biological sequence representation today.

## Key idea

The core of contrastive learning is to learn a representation space where semantically similar samples are pulled together and dissimilar ones are pushed apart. For biological sequences (RNA, proteins), "similarity" can be defined from multiple perspectives: sequence homology, functional annotation, or structural similarity.

## Connection to our work

One paper used a cross-context approach to construct positive/negative pairs, which resonates with the design philosophy behind DeepRDR — leveraging associations across different contexts to enhance representations.

## TODO

- Summarize variants of contrastive loss functions
- Run ablation experiments on the gated cross fusion module
- Prepare response plan for potential reviewer comments
