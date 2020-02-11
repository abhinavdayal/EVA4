# S4

Answers to questions asked:
* Batch Normalization is always a good practice to add because it emphasizes the features learned
* Dropouts are necessary only if the gap between train and test is large. I tried without dropouts and then used a small dropout to close in the gap
* 1x1 conv is used at the end to reduce the number if channels to 10.
* GAP is used to flatten the channels before applying softmax

## Without drouputs
Used Batch Normalization, No dropouts, Single maxpooling layer, a 1x1 conv at end to reduce to 10 channels and a GAP layer.

https://github.com/abhinavdayal/EVA4/blob/master/S4/EVA4_Session_2_Success04_WO_Droputs.ipynb

```
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1            [-1, 8, 26, 26]              72
       BatchNorm2d-2            [-1, 8, 26, 26]              16
            Conv2d-3            [-1, 8, 24, 24]             576
       BatchNorm2d-4            [-1, 8, 24, 24]              16
            Conv2d-5            [-1, 8, 22, 22]             576
       BatchNorm2d-6            [-1, 8, 22, 22]              16
            Conv2d-7            [-1, 8, 20, 20]             576
       BatchNorm2d-8            [-1, 8, 20, 20]              16
         MaxPool2d-9            [-1, 8, 10, 10]               0
           Conv2d-10             [-1, 16, 8, 8]           1,152
      BatchNorm2d-11             [-1, 16, 8, 8]              32
           Conv2d-12             [-1, 16, 6, 6]           2,304
      BatchNorm2d-13             [-1, 16, 6, 6]              32
           Conv2d-14             [-1, 16, 4, 4]           2,304
      BatchNorm2d-15             [-1, 16, 4, 4]              32
           Conv2d-16             [-1, 16, 2, 2]           2,304
      BatchNorm2d-17             [-1, 16, 2, 2]              32
           Conv2d-18             [-1, 10, 2, 2]             160
================================================================
Total params: 10,216
Trainable params: 10,216
Non-trainable params: 0
----------------------------------------------------------------
```

### Outcome: **99.4** validation accuracy at epoch 13
```
Epoch: 13
Train set: Average loss: 0.0174, Accuracy: 59675/60000 (99.46%)
Test set: Average loss: 0.0188, Accuracy: 9940/10000 (99.40%)
```

## With dropouts
Towards the end the train accuracy was 99.75 so added 5% dropouts as another experiment and got slightly better results.

https://github.com/abhinavdayal/EVA4/blob/master/S4/EVA4_Session_2_Success04.ipynb


```
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1            [-1, 8, 26, 26]              72
           Dropout-2            [-1, 8, 26, 26]               0
       BatchNorm2d-3            [-1, 8, 26, 26]              16
            Conv2d-4            [-1, 8, 24, 24]             576
           Dropout-5            [-1, 8, 24, 24]               0
       BatchNorm2d-6            [-1, 8, 24, 24]              16
            Conv2d-7            [-1, 8, 22, 22]             576
           Dropout-8            [-1, 8, 22, 22]               0
       BatchNorm2d-9            [-1, 8, 22, 22]              16
           Conv2d-10            [-1, 8, 20, 20]             576
          Dropout-11            [-1, 8, 20, 20]               0
      BatchNorm2d-12            [-1, 8, 20, 20]              16
        MaxPool2d-13            [-1, 8, 10, 10]               0
           Conv2d-14             [-1, 16, 8, 8]           1,152
          Dropout-15             [-1, 16, 8, 8]               0
      BatchNorm2d-16             [-1, 16, 8, 8]              32
           Conv2d-17             [-1, 16, 6, 6]           2,304
          Dropout-18             [-1, 16, 6, 6]               0
      BatchNorm2d-19             [-1, 16, 6, 6]              32
           Conv2d-20             [-1, 16, 4, 4]           2,304
          Dropout-21             [-1, 16, 4, 4]               0
      BatchNorm2d-22             [-1, 16, 4, 4]              32
           Conv2d-23             [-1, 16, 2, 2]           2,304
          Dropout-24             [-1, 16, 2, 2]               0
      BatchNorm2d-25             [-1, 16, 2, 2]              32
           Conv2d-26             [-1, 10, 2, 2]             160
================================================================
Total params: 10,216
Trainable params: 10,216
Non-trainable params: 0
----------------------------------------------------------------
```
### Output Validation Accuracy of 99.41 at 13th Epoch and 99.43 at 20th
This was expected as drouput regularization should have reduced the gap between training and test accuracy.

```
Epoch: 13
Train set: Average loss: 0.0256, Accuracy: 59522/60000 (99.20%)
Test set: Average loss: 0.0195, Accuracy: 9941/10000 (99.41%)
```

---

## Other experiments

### 99.48 accuracy with 19.2k parameters in 20th Epoch
Used 2 max pooling layers.

https://github.com/abhinavdayal/EVA4/blob/master/S4/EVA4_Session_2_Success01.ipynb


