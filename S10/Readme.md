# S10

[Link to notebook](https://github.com/abhinavdayal/EVA4/blob/master/S10/EVA04_S10_Resnet18_Albumentations_Gradcam_LRFinder.ipynb)

* Moved library to separate repository [here](https://github.com/abhinavdayal/EVA4_LIBRARY). 
* Implemented LR Finder [here](https://github.com/abhinavdayal/EVA4_LIBRARY/blob/master/EVA4/eva4LRFinder.py).
* used the best LR as starting point for LR Reduce on plateau with patience of 2
* ran for 50 epochs using Resnet 18 model on CFAR10 with SGD, nexterov with momentum and L2 regularization of 0.0001. Got 92.47 accuracy in 49th Epoch.

## Learning Rate finder plot
![LRfinder](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/LRRange.png)

## Performance plots

![accuracy](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/accuracylr.png)

![loss](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/losslr.png)

## 25 misclassified images

![misclassifications](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/misclassifications.png)

## Gradcams of misclassified images

![10](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/gcams10.png)
![20](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/gcams20.png)
![25](https://github.com/abhinavdayal/EVA4/blob/master/S10/images/gcams25.png)

# Conclusions
The results clearly indicate overfitting. This we need to address probably using regularization or more rigorous augmentation. One issue is the image sizes being too small 32x32 for the resnet18 with a very high receptive field. Probably a simpler model would work better.
