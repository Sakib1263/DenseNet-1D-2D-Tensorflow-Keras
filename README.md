# DenseNet-Model-Builder-Tensorflow-Keras  
Models Supported: 
1. DenseNet121, DenseNet169, DenseNet201, DenseNet264 [Reference: https://arxiv.org/abs/1608.06993]
2. DenseNet161 (Extra) [Reference: https://pytorch.org/hub/pytorch_vision_densenet/]

## DenseNet Architecture  
Detail architecture for various versions of DenseNet is provided in the following table from the Original preprint [1].  
![DenseNet Architectures Params](https://github.com/Sakib1263/DenseNet-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/DenseNet_Table.png "DenseNet Architectures")  

Here it can be seen that, after initial Convolution (7x7) and Pooling layer (similar to the ResNets [3]), there is a repitition of Dense Blocks and Transitions Blocks. The Transition Blocks contain an (1x1) Convolutional Layer and Average-Pooling. While the Dense Blocks contain multiple iterations (or layers) of (1x1 Conv Block + 3x3 Conv Block). The number of iterations for the 3rd and 4th Dense block vary for each model. In the end, there is a Global Pooling layer followed by an Multi Layer Perceptron (MLP) layer (which might differ in structure based on the model type e.g., Classification or regression). A 3D view of a singla Dense Block of 5 layers has been presented in the figure below [1].

![DenseNet Architectures Params](https://github.com/Sakib1263/DenseNet-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/Dense_Block.png "DenseNet Architectures")  

