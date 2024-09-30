# Binary Image Classification with MobileNetV2 Using Transfer Learning

## Project Overview 

This project focuses on utilizing transfer learning with the MobileNetV2/VGG16 architectures to perform binary classification on brain MRI images. The objective is to identify the presence of brain tumors in MRI scans. The dataset used is the Brain MRI Images for Brain Tumor Detection from Kaggle, which includes two classes: "Tumor" and "No Tumor.".


### Dataset: 

The dataset contains MRI images that are pre-labeled into two categories. After performing data preprocessing, such as resizing the images to fit the MobileNetV2 input requirements and label encoding, the data is fed into the model

### Model: MobileNetV2

MobileNetV2 is a lightweight and efficient convolutional neural network (CNN) architecture developed by Google for mobile and embedded vision applications. It is designed to perform well on classification tasks with lower computational resources.

### Model: VGG16

VGG16 is a deep convolutional neural network developed by the Visual Geometry Group (VGG) at Oxford, known for its simplicity and effectiveness in image classification tasks. It has 16 layers, including 13 convolutional layers with small 3x3 filters, followed by 3 fully connected layers. Max-pooling is applied after groups of convolutions to reduce spatial dimensions. VGG16 uses ReLU activation and is often used in transfer learning due to its pre-trained weights on the large ImageNet dataset. Despite its high accuracy, it has a large number of parameters, making it computationally intensive compared to newer models.

#### Pre-trained on ImageNet: 
The model used in this project is pre-trained on the ImageNet dataset, allowing us to leverage pre-learned features, a technique known as transfer learning. This helps improve accuracy even with small datasets.

#### Key Features of MobileNetV2:

- Depthwise separable convolutions for computational efficiency.
- A linear bottleneck structure to reduce complexity while preserving features.
- Inverted residuals to improve memory efficiency and reduce computation.

### Key Features of VGG16:
- 3x3 convolutional filters throughout the network for consistency and simplicity.
- Max-pooling layers to reduce the spatial dimensions of feature maps.
- Deep architecture with 16 weight layers, including 13 convolutional and 3 fully connected layers.
- ReLU activation functions after each layer to introduce non-linearity.
- Pre-trained on ImageNet, making it a powerful model for transfer learning applications.

### 4. Model Architecture and Transfer Learning

#### Base Model:
The pre-trained models were used, excluding the top (fully connected) layers. These layers were replaced with custom layers suited to our binary classification task.

#### Custom Layers:

A GlobalAveragePooling2D layer was added to reduce the dimensionality of the feature map.
Two dense layers with 1024,512 units and ReLU activation followed by a final output layer.

#### Freezing the Base Model: 
The base model was frozen to prevent its weights from being updated during training. Only the newly added layers were trained.

### 6. Model Evaluation and Prediction

The model was evaluated on a test set and demonstrated excellent performance.

