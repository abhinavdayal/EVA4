# S8

Used Resnet 18 as suggested ([Link](https://github.com/abhinavdayal/EVA4/blob/master/S8/EVA04_S8_Resnet18.ipynb)). But replaced FC layer with 1x1 after GAP as it was initially told that in EVA 4 we will never use FC layer.

Got 85+ accuracy in 8th Epoch and 91.61 in 20th Epoch. Only trained for 20 epochs.

The rest of the [library](https://github.com/abhinavdayal/EVA4/tree/master/S7/EVA4library) is as in S7.

Added [new model for Resnet18](https://github.com/abhinavdayal/EVA4/blob/master/S8/eva4resnet.py) deriving from Net base class of S7.
