---
layout: default_paper
id: 10
order: 114
poster_session: 3
session_id: 8
title: "Importance of Self-Consistency in Active Learning for Semantic Segmentation"
authors:
  - author: "S. Alireza Golestaneh (Carnegie Mellon University)"
  - author: "Kris Kitani (CMU)"
all_authors: "S. Alireza Golestaneh and Kris Kitani"
code: ""
keywords:
  - word: "Active Learning"
  - word: "Semantic Segmentation"
  - word: "Self-Supervised Learing"
  - word: "Self-Consistency"
  - word: "Uncertainty"
paper: "papers/0010.pdf"
supp: ""
abstract: "We address the task of active learning in the context of semantic segmentation and show that self-consistency can be a powerful source of self-supervision to greatly improve the performance of a data-driven model with access to only a small amount of labeled data. Self-consistency uses the simple observation that the results of semantic segmentation for a specific image should not change under transformations like horizontal flipping (i.e.,  the results should only be flipped). In other words, the output of a model should be consistent under equivariant transformations. 
The self-supervisory signal of self-consistency is particularly helpful during active learning since the model is prone to overfitting when there is only a small amount of labeled training data. 
In our proposed active learning framework, we iteratively extract small image patches that need to be labeled, by selecting image patches that have high uncertainty (high entropy) under equivariant transformations. 
We enforce pixel-wise self-consistency between the outputs of the segmentation network for each image and its transformation (horizontally flipped) to utilize the rich self-supervisory information and reduce the uncertainty of the network.
In this way, we are able to find the image patches over which the current model struggles the most to classify. By iteratively training over these difficult image patches, our experiments show that our active learning approach reaches 96% of the top performance of a model trained on all data, by using only 12% of the total data on benchmark semantic segmentation datasets (e.g., CamVid and Cityscapes)."
slides-id: 38933864
channel-id: "paper_114_P3_id_0010"
---
