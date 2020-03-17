# S9

[Link to assignment](https://github.com/abhinavdayal/EVA4/blob/master/S9/EVA04_S9_Resnet18_Albumentations_Gradcam.ipynb)
* We did Albumentation library augmentation and tried cutout, horizontal flip, rgb shift and Rortate along with Normalize and ToTensor
* test transform in only Normalize and ToTensor
* We implemented Gradcam using help from [this library](https://github.com/kazuto1011/grad-cam-pytorch).
* We tested gradcam with both cutout etc. and no transformations other than nortmalize. Results were interesting. In fact on some images it didnt predict well. And we visualize all 4 layer outputs of ResNet. Lots of learning.

# changes to library

* added gradcam functionality
* added Albumentation transforms

