# Classification-of-Urdu-MNIST-dataset
Using pre-trained models of ResNet-50 and VGG16 for classification of Urdu MNIST dataset.

The dataset consisted of 7440 (263 x 173) color images in 12 classes, with 620 images per class. There are 6000 training images and 1440 test images.

![Image Samples](Image/data.PNG?raw=true "Title")

Library: Pytorch
Environment: Colab (Mounted drive)

Following steps were followed for using pre-trained models of ResNet-50 and Vgg16:
- Mounting of drive on Colab
- Data preparation and Transformation
- Transformation involved resizing, making tensors and normalization
- Getting pre-trained models
- Setting of gradient propagation flag to false as we do not want to update pre-trained model
- Updating the FC layer with out_features as our number of classes in the ResNet-50 which gave (fc): Linear(in_features=2048, out_features=12, bias=True)

- Removing the FC layer and adding FC layer using training number of classes in the VGG16 which gave Linear(in_features=25088, out_features=4096, bias=True) (1): ReLU(inplace) (2): Dropout(p=0.5) (3): Linear(in_features=4096, out_features=4096, bias=True) (4): ReLU(inplace) (5): Dropout(p=0.5) (6): Linear(in_features=4096, out_features=12, bias=True)
- Used cross entropy loss and for optimizer used SGD with lr = 0.01 & momentum 0.9
- Training
- Testing and Calculation of accuracy

## Loss
Loss after 10 Epochs for ResNet-50 training = 0.1093 Loss after 10 Epochs for VGG16 training = 0.8144

## Accuracy
Accuracy of the ResNet-50 on the 1440 test images = 99% Accuracy of the VGG16 on the 1440 test images = 98%


