# S12

## Assignment A - First attempt

* implemented [tinyimage dataset](https://raw.githubusercontent.com/abhinavdayal/EVA4_LIBRARY/master/EVA4/eva4datasets/tinyimagenet.py) to load the dataset with 70/30 split

* [Trained Resnet 18](https://github.com/abhinavdayal/EVA4/blob/master/S12/S12_Assignment_Success1.ipynb) for 50 Epochs using Augmentations: FlipLR, Cutout, RandomCrop, rotation, and RGB Shift, with One Cycle LR policy for SGD with momentum

* Got validation accuracy of 61.93%

### Observations
* Training accuracy is over 93% so there is overfitting. Need to have harsher augmentations. 
* Adam can probably work better than SGD as we have less images per class. However on trying it was way too slow and gave out of memory in colab


## Assignment A - Second attempt

* [Trained Resnet 18](https://github.com/abhinavdayal/EVA4/blob/master/S12/S12_Assignment_Success2.ipynb) for 50 Epochs using Augmentations: FlipLR, harsher random cutout, random grayscale, zoom, rotation with One Cycle LR policy for SGD with momentum

* Got validation accuracy of 62.61%

### Observations
* Gap between train/test reduced. Train accuracy reached little over 78% only this time. So probably on further training, can get better accuracy.
* can reduce grayscale transform probability to 0.2 or below. Ideally the network should do the transform, but we are giving a headstart.

## Assignment B
* Downloaded [50 dog images](https://github.com/abhinavdayal/EVA4Data/tree/master/Dogs)
* Annotated the bounding boxes and got [this json](https://raw.githubusercontent.com/abhinavdayal/EVA4Data/master/Dogs_annotations.json). 

![annotation details](https://raw.githubusercontent.com/abhinavdayal/EVA4Data/master/labeled_annotation.png)

* Found [best clusters here](https://github.com/abhinavdayal/EVA4/blob/master/S12/S12_YOLO_Anchor_Boxes.ipynb). 
* Did standard kmeans and also custom kmeans with distance defined as 1 - IOU between cluster center and bbox
* plotted centroid vs mean IOU as well as best anchor boxes
* adjusted cluster membership according to highest IOU match rather than kmeans metric in sklearn method

![IOUplot](https://raw.githubusercontent.com/abhinavdayal/EVA4/master/S12/IOUplot.png)

![3 lusters](https://raw.githubusercontent.com/abhinavdayal/EVA4/master/S12/cluster3.png)
![3 abox](https://raw.githubusercontent.com/abhinavdayal/EVA4/master/S12/abox3.png)

![5 lusters](https://raw.githubusercontent.com/abhinavdayal/EVA4/master/S12/cluster5.png)
![5 abox](https://raw.githubusercontent.com/abhinavdayal/EVA4/master/S12/abox5.png)

* k=3 is sufficient, but k=5 may also be used
