# simclr
This repository contains a PyTorch implementation of SimCLR based on the work [A Simple Framework for Contrastive Learning of Visual Representations](https://arxiv.org/abs/2002.05709) by Chen et al.

SimCLR consists of 4 elements:

- a random data augmentation (crops and color jitter)
- a base encoder (ResNet50)
- a projection head (2 layer MLP)
- a contrastive loss (NT-Xent)

Each input image is randomly tranformed twice. The task is to identify the second transformation among a batch of other source images. For efficiency, the other images in the batch are used as negative examples and the loss is calculated based on pairwise cosine similarities.

## TODOs

- [ ] LARS instead of Adam
- [ ] Same LR schedule

## Results

### CIFAR-10

Linear evalutation using modified ResNet50, t=0.5, bs=256.

| Source    | Epoch 100 | Epoch 200 | Epoch 300 | Epoch 400 | Epoch 500 |
| --------- | ---------:| ---------:| ---------:| ---------:| ---------:|
| Paper     | 83.9%     | 89.2%     | 91.5%     | 92.1%     | 93.0%     |
| This repo | 77.9%     |           |           |           |           |

As shown in Fugure B.6. These numbers aren't final yet.
