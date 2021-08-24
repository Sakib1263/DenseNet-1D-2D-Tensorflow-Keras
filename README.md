# DenseNet-Model-Builder-Tensorflow-Keras  
Models Supported: 
1. DenseNet121, DenseNet169, DenseNet201, DenseNet264 [1]
2. DenseNet161 (Extra) [2]

## DenseNet Architecture  
Detail architecture for various versions of DenseNet is provided in the following table from the Original preprint [1].  
![DenseNet Architectures Params](https://github.com/Sakib1263/DenseNet-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/DenseNet_Table.png "DenseNet Architectures")  

Here it can be seen that, after initial Convolution (7x7) and Pooling layer (similar to the ResNets [3]), there is a repitition of Dense Blocks and Transitions Blocks. The Transition Blocks contain an (1x1) Convolutional Layer and Average-Pooling. While the Dense Blocks contain multiple iterations (or layers) of (1x1 Conv Block + 3x3 Conv Block). The number of iterations for the 3rd and 4th Dense block vary for each model. In the end, there is a Global Pooling layer followed by an Multi Layer Perceptron (MLP) layer (which might differ in structure based on the model type e.g., Classification or regression). A 3D view of a singla Dense Block of 5 layers has been presented in the figure below [1].

![DenseNet Architectures Params](https://github.com/Sakib1263/DenseNet-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/Dense_Block.png "DenseNet Architectures")  
Here it can be seen that inside the Dense Blocks, there are residual or skip connections from one layer to every other layer. During implementation, all layers are concatenated.  

## Supported Features  
The speciality about this model is its flexibility. The user has the option for: 
1. Choosing any of 5 available DenseNet models for either 1D or 2D tasks.
2. Varying number of input kernel/filter, commonly known as the Width of the model.
3. Varying number of classes for Classification tasks and number of extracted features for Regression tasks.
4. Varying number of Channels in the Input Dataset.  
5. Optional turnoff of the Bottleneck Architecture: The bottleneck structure of the Dense Blocks can be removed by avoiding the 1x1 Conv block in each layer. Turning off the Bottleneck structure will make the model lighter but performance might vary.  
For DenseNet (especially for the deeper models), it is necessary to be careful about the overwhelming number of paramaters resulting just from a slight increase of model width or kernel size due to the bulkiness of the model (which might result into a RAM or session crash). 

## References  
[1] 
[2] 
[3] 
