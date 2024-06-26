## LUNG CANCER CLASSIFICATION USING VGG16

VGG16 Model Overview:

Architecture:
- Layers: 16 weight layers (13 convolutional layers + 3 fully connected layers).
- Conv Layers: Small 3x3 receptive fields, stacked for deeper architecture.
- Pooling: Max-pooling layers (2x2) follow some of the conv layers.
- FC Layers: Three fully connected layers at the end, with softmax activation in the final layer for classification.
  
Design Principles:
- Use of small convolutional filters (3x3) and consistent design.
- Trained on ImageNet in 2014.
  
Considerations:
- Can only work with RGB images
- Expects image size of 224 x 224 pixels.
  
TECHNICAL IMPLEMENTATION

1. Data Preparation:
- Loaded a Lung Cancer Classification dataset from Kaggle.
- Resized images to 224x224 pixels to match the input size expected by VGG16.
- Kept the channel dimension to 3 as expected by VGG16 model
- Used os module for path construction
  
2.Model Architecture:
- Used VGG16 pre-trained on ImageNet as the feature extractor.
- Added custom top layers including Global Average Pooling and Dense layers to adapt the model for our specific classification task.

3. Transfer Learning:
- Frozen the pre-trained VGG16 layers to retain learned features.
- Fine-tuned the custom top layers to adapt to the new dataset.
  
4. Training:
- Split the dataset into training and testing sets (80/20 split).
- Trained the model using categorical cross-entropy loss and Adam optimizer.
- Evaluated the model on the test set, achieving accuracy of 98%.
