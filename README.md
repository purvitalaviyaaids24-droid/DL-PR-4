CIFAR-10 Image Classification Using CNNs
Project Overview
This project explores image classification using the CIFAR-10 dataset
and TensorFlow/Keras. It introduces the core concepts behind
Convolutional Neural Networks (CNNs), builds and trains a CNN, and
compares approaches such as data augmentation and transfer learning.
Objectives
Load and explore the CIFAR-10 image dataset.
Understand image preprocessing, pixel normalization, and one-hot
encoding.
Demonstrate convolution, filters, feature maps, padding, stride,
pooling, and flattening.
Build a LeNet-5-style model and a custom CNN.
Train a CNN and monitor training/validation performance.
Compare an original CNN with data-augmentation approaches.
Apply transfer learning with MobileNetV2 using feature extraction
and fine-tuning.
Review the purpose of residual connections in deep networks.
Dataset
The notebook uses the CIFAR-10 dataset available through
tensorflow.keras.datasets. It contains 60,000 colour images of size 32
× 32 pixels across 10 classes.
Label Class

    0 Airplane
    1 Automobile
    2 Bird
    3 Cat
    4 Deer
    5 Dog
    6 Frog
    7 Horse
    8 Ship
    9 Truck
The standard dataset split contains 50,000 training images and 10,000
test images.
Technologies and Libraries
Python
Jupyter Notebook
NumPy
Matplotlib
TensorFlow
Keras
Project Workflow
1.Load and inspect the data --- check array shapes, labels, and
example images.
2.Preprocess images --- scale pixel values from 0--255 to 0--1 and
convert labels to one-hot vectors.
3.Explore CNN operations --- convert an image to grayscale, apply
a hand-built edge-detection kernel, and inspect convolution outputs.
4.Study feature extraction --- demonstrate convolution layers,
VALID and SAME padding, stride, feature maps, max pooling,
average pooling, and flattening.
5.Build model architectures --- inspect a LeNet-5-style network
and create a custom CNN.
6.Train the CNN --- use Adam optimization and categorical
cross-entropy, with early stopping and learning-rate reduction
callbacks.
7.Evaluate training behaviour --- plot loss and accuracy for
training and validation data.
8.Experiment with data augmentation --- compare the original CNN
with augmentation using image transformations.
9.Explore transfer learning --- resize images to 96 × 96, use
ImageNet-pretrained MobileNetV2, train a classification head, then
fine-tune selected layers.
10.Review residual connections --- explain how shortcut connections
can help gradient flow in deeper networks.
Custom CNN Architecture
The notebook's custom CNN follows this general structure:
Input: 32 × 32 × 3 RGB image
Two 32-filter convolution layers with ReLU activation
Max pooling
Two 64-filter convolution layers with ReLU activation
Max pooling
One 128-filter convolution layer
Global average pooling
Dense layer with 256 units and ReLU activation
Output layer with 10 units and softmax activation
The output layer returns a probability distribution over the ten
CIFAR-10 classes.
Training Configuration
The main CNN is compiled with: - Optimizer: Adam - Loss:
Categorical cross-entropy - Metric: Accuracy - Batch size: 64 -
Maximum epochs: 50 - Validation split: 10% - Callbacks:
Early stopping and ReduceLROnPlateau
The notebook also trains augmentation-based models and a MobileNetV2
transfer-learning model. Exact accuracy values depend on execution,
environment, and training settings; run the notebook to obtain your
results.
How to Run
1.Download or clone this project and open PR_4.ipynb in Jupyter
Notebook or JupyterLab.
2.Ensure Python and the required libraries are installed.
3.Run the notebook cells in order.
Install the main dependencies if needed:
pip install numpy matplotlib tensorflow jupyter
The CIFAR-10 dataset is downloaded by Keras on first use, so an internet
connection may be required during initial setup. MobileNetV2 also uses
ImageNet pretrained weights, which may be downloaded when the model is
created.
Results and Observations
The notebook generates visualizations and printed outputs for dataset
exploration, convolution operations, feature maps, model summaries,
training/validation curves, and test-set accuracy comparisons.
Add your measured results after running the notebook:

Model / Experiment Test Accuracy

Custom CNN Add result from notebook
CNN with image-data-generator Add result from notebook
augmentation 
CNN with Keras augmentation Add result from notebook
layers 
MobileNetV2 feature extraction Add result from notebook
MobileNetV2 fine-tuning Add result from notebook
Do not fill in these values until the corresponding evaluation cells
have run.
Key Learnings
Normalizing input pixels helps keep values on a consistent scale.
Convolutional filters learn spatial features from images.
Pooling reduces feature-map dimensions while retaining useful
information.
Data augmentation increases training-image variety and may help
reduce overfitting.
Transfer learning reuses pretrained features and can be adapted to a
new classification task.
Training and validation curves help diagnose model learning
behaviour.
Project Structure
.
├── PR_4.ipynb
└── README.md
Future Improvements
Add a confusion matrix and per-class precision, recall, and
F1-score.
Display sample predictions alongside their true labels.
Compare architectures using consistent training and validation
settings.
Save the best trained model and document reproducible results.
Track experiments, training time, and model size.
Author
Purvi Talaviya
