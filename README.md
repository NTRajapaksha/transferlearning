# Binary Image Classification with MobileNetV2 Using Transfer Learning

This project demonstrates binary image classification using transfer learning with the MobileNetV2 model. The goal is to classify images as either "people crossing the road" or "empty roads." The project includes all necessary steps, from data collection to model training and evaluation, achieving high accuracy.


## Project Overview

### 1. Data Collection and Preprocessing

#### Image Sourcing: 
The dataset consists of images scraped directly from Google Images. Two categories of images were extracted:

Images of people crossing the road.
Images of empty roads.

#### Preprocessing: 
A data-cleaning step was implemented to remove corrupted or improperly formatted images. This was done using a script that filters images based on supported formats (e.g., JPEG, 
PNG) and removes any invalid ones.

### 2. Data Augmentation and Preparation

To enhance the model's generalization ability, data augmentation techniques were applied to artificially expand the dataset. These techniques included:

Random rotations.
Flipping.
Zooming.

### 3. Model: MobileNetV2

MobileNetV2 is a lightweight and efficient convolutional neural network (CNN) architecture developed by Google for mobile and embedded vision applications. It is designed to perform well on classification tasks with lower computational resources.

#### Pre-trained on ImageNet: The model used in this project is pre-trained on the ImageNet dataset, allowing us to leverage pre-learned features, a technique known as transfer learning. This helps improve accuracy even with small datasets.

#### Key Features of MobileNetV2:

Depthwise separable convolutions for computational efficiency.
A linear bottleneck structure to reduce complexity while preserving features.
Inverted residuals to improve memory efficiency and reduce computation.

### 4. Model Architecture and Transfer Learning

#### Base Model:
The pre-trained MobileNetV2 model was used, excluding the top (fully connected) layers. These layers were replaced with custom layers suited to our binary classification task.

#### Custom Layers:

A GlobalAveragePooling2D layer was added to reduce the dimensionality of the feature map.
A dense layer with 512 units and ReLU activation followed by a final dense layer with 1 unit and a sigmoid activation for binary classification.

#### Freezing the Base Model: 
The base MobileNetV2 model was frozen to prevent its weights from being updated during training. Only the newly added layers were trained.

### 5. Training the Model

The model was trained using a low learning rate (due to the small dataset size) to fine-tune the network gradually, avoiding overfitting.
The binary cross-entropy loss function was used, which is standard for binary classification tasks.

Optimizer: Adam optimizer was chosen for its adaptive learning rate capabilities.
### Evaluation: After training, the model achieved an impressive 99% accuracy on the validation set.

### 6. Model Evaluation and Prediction

The model was evaluated on a test set and demonstrated excellent performance.
A custom function was used to visualize predictions on test images, showing the model's ability to correctly classify unseen data.
