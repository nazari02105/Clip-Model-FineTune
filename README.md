# Clip-Model-FineTune
In this repository, we fine-tune the Clip model step by step using the CIFAR10 and CRC datasets.

# Cifar10 Dataset
## No Augmentation and No Finetune
In [this file](./Cifar10FineTune/1-NoFineTuneNoAugmentation.ipynb), before using Clip and other methods, we trained a simple network on the Cifar10 dataset to see the initial accuracy without Clip and be able to compare. No specific techniques such as augmentation or LR Scheduler have been applied in this file.
## No Finetune With Augmentation
In [this file](./Cifar10FineTune/2-NoFineTuneWIthAugmentation.ipynb), which is quite similar to the previous section, some improvements such as augmentation, lr scheduler, weight decay, etc. have been added and the accuracy has improved compared to before.
## No Augmentation With Finetune (Without Freezing any Layers)
In [this file](./Cifar10FineTune/3-NoAugmentationWithFineTune.ipynb), I removed the augmentation, scheduling, etc. and wanted to see how the accuracy would change only by fine-tuning. Moreover, we can fine-tune in several ways, and in [this file](./Cifar10FineTune/3-NoAugmentationWithFineTune.ipynb), I did it without freezing any layers, even the layers related to the Clip model were not frozen.
## No Augmentation With Finetune (With Freezing Clip Part Layers)
In [this file](./Cifar10FineTune/4-NoAugmentationWithFineTune.ipynb), which is almost similar to the previous section, the only addition is that the layers of the Clip section of the model have been frozen and only the head of the model is updated.
## No Augmentation With Finetune (With Freezing Clip Part Layers After 2 Epochs)
In [this file](./Cifar10FineTune/5-NoAugmentationWithFineTune.ipynb), which is exactly like the previous two sections, I froze the Clip layers but not from the beginning, and I did this after two epochs.
## Finetune With Augmentation (Without Freezing any Layers)
Since the best accuracy in cases without augmentation was achieved when no freezing was done, I applied this case without freezing and also applied the same factors such as lr scheduling, weight decay, etc in [this file](./Cifar10FineTune/6-FineTuneWithAugmentation.ipynb).
# CRC Dataset
## Finetune With Augmentation
In [this file](./CRCFineTune/NoAugmentationWithFineTune.ipynb), first of all, the main dataset was downloaded, and one of the most important steps was to find the ROI (region of interest). Because in each image, there is a lot of non-tissue area, and for this reason, it is better not to include them in the network learning process. For this purpose, I used the Otsu threshold and found the ROI by converting it to the HSV space. However, the result was not good, and many non-tissue areas were still considered as ROI. So I used morphological operations with different kernels and opening and closing operations to optimize this ROI. Therefore, the mask of each image is created, and patches are generated based on it. Since generating patches was very time-consuming, I limited the amount of the dataset and trained the model on a small part of it, but if you want, you can remove this limitation. Finally, as in the previous sections, I added the network and lr_schedule and weight decay, and achieved a very good accuracy.
<p align="center">
  <img src="https://i.ibb.co/QfR8kS4/2023-04-28-10h19-27.png"/>
  <br/>
  a) refers to the original image. b) is for using HSV channels and otsu threshold. c) is after applying morphology and different kernels.
</p>
