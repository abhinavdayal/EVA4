# S8

Used Resnet 18 as suggested. But replaced FC layer with 1x1 after GAP as it was initially told that in EVA 4 we will never use FC layer.

Got 85+ accuracy in 8th Epoch and 91.61 in 20th Epoch. Only trained for 20 epochs.

The rest of the library is as in S7.

Added new model for Resnet18 deriving from Net base class of S7.
