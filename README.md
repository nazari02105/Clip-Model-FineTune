# Clip-Model-FineTune
In this repository, we fine-tune the Clip model step by step using the CIFAR10 and CRC datasets.

# Cifar10 Dataset
## No Augmentation and No Finetune
In [this file](./Cifar10FineTune/1-NoFineTuneNoAugmentation.ipynb), before using Clip and other methods, we trained a simple network on the Cifar10 dataset to see the initial accuracy without Clip and be able to compare. No specific techniques such as augmentation or LR Scheduler have been applied in this file.
## No Finetune With Augmentation
In [this file](./Cifar10FineTune/2-NoFineTuneWithAugmentation.ipynb), which is quite similar to the previous section, some improvements such as augmentation, lr scheduler, weight decay, etc. have been added and the accuracy has improved compared to before.
## No Augmentation With Finetune (Without Freezing any layers)
In [this file](./Cifar10FineTune/3-NoAugmentationWithFineTune.ipynb), I removed the augmentation, scheduling, etc. and wanted to see how the accuracy would change only by fine-tuning. Moreover, we can fine-tune in several ways, and in [this file](./Cifar10FineTune/3-NoAugmentationWithFineTune.ipynb), I did it without freezing any layers, even the layers related to the Clip model were not frozen.
