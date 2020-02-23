# simclr
This repository contains a PyTorch implementation of SimCLR based on the work [A Simple Framework for Contrastive Learning of Visual Representations](https://arxiv.org/abs/2002.05709) by Chen et al. Due to hardware limitations I'm focussing on the CIFAR-10 case.

SimCLR consists of 4 elements:

- a random data augmentation (crops and color adjustments)
- a base encoder (ResNet50)
- a projection head (2 layer MLP)
- a contrastive loss (NT-Xent)

Each input image is randomly tranformed twice. The task is to identify the second transformation among a batch of other source images. For efficiency, the other images in the batch are used as negative examples and the loss is calculated based on pairwise cosine similarities.
