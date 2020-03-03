# S7

We did all the required things:

1. We started with 400K odd parameters with 1 dilated conv in parallel and two depth separated conv. Got 80+ accuracy in 5th Epoch
2. Reduced to 120K params and got 80+ accuracy in 8 epochs
3. Replaced all conv to depthwaise separable reducing to 40K params and got 80+ accuracy in 18 Epochs
4. Moved dialated conv to main layer in first conv block. Removed depthwise except in last conv block. 100K params got 80+ accuracy in 9th Epoch
5. Reduced dual conv in each block to single dialated conv with dilation of 2. 50K params. Reached 80+ accuracy in 20th Epoch
