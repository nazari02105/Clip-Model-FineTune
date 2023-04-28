# Clip-Model-FineTune
In this repository, we fine-tune the Clip model step by step using the CIFAR10 and CRC datasets.

# Cifar10 Dataset
## No Augmentation and No Finetune
In [this file](./Cifar10FineTune/1-NoFineTuneNoAugmentation.ipynb), before using Clip and other methods, we trained a simple network on the Cifar10 dataset to see the initial accuracy without Clip and be able to compare. No specific techniques such as augmentation or LR Scheduler have been applied in this file.
## No Finetune With Augmentation
In [this file](./Cifar10FineTune/۲-NoFineTuneWithAugmentation.ipynb), which is quite similar to the previous section, some improvements such as augmentation, lr scheduler, weight decay, etc. have been added and the accuracy has improved compared to before.
