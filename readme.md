# Introduction

This project demonstrates the implementation of a face recognition system using Siamese networks. Siamese networks are widely used in face recognition tasks because they can effectively measure the similarity between two images, making them ideal for verification and identification purposes.

## Approach

1)Our project started with learning the basics of deep learning and neural networks.

2)With the knowledge of Gradient Descent Backpropagation Algorithm and other basics we implemented digit classifier 1 layer neural network using basic numpy module.

3)Then we moved on with learning model optimization techniques like batch normalization and dropout to counter problems like overfitting, after which we implemented the same digit classifier model using pytorch framework.

4)Then, we learnt the working of Convolutional Neural Networks and studied various CNN Architectures.

5)With a good understanding of CNN's, after many trials, we built our own custom architecture on MNIST/CIFAR-10 Dataset that efficiently did the classification tasks.

6)Finally we leant the concepts of Face Recognition and moved on with the implementation.

## The Algorithm

### Siamese Networks

* A Siamese network consists of two identical subnetworks that share the same architecture and parameters. These twin networks process two separate inputs in parallel.

* Siamese networks are primarily used for comparing pairs of data points. These inputs could be images, texts, or any other kind of data that can be represented numerically.

* Each twin network converts its input into a lower-dimensional representation known as an "embedding." The embedding is a vector of numerical values that captures essential features of the input data. The network is trained to ensure that the embeddings of similar input pairs are close in the embedding space, and those of dissimilar pairs are far apart.

* One crucial aspect of Siamese networks is that the twin networks share the same set of weights. This weight sharing ensures that the two networks learn to map inputs to embeddings in a consistent and compatible manner.

![Siamese Architecture](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*hBJRs10uBc9a2Ol10N-jlg.png)

### Contrastive Loss
This is the loss function used for learning the similarity function.

![Loss Formula](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*QE2ccvCNw6HOW85e.png)

where Dw is defined as the Euclidean distance between the outputs of the sister networks.
Y is either 1 or 0. If the first image and second image are from the same class, then the value of Y is 0, otherwise, Y is 1

## Implementation

- **Siamese Network**: The core of the project is the Siamese network model. This model consists of convolutional and fully connected layers that learn to extract discriminative features from face images. It is defined in the `SiameseNetwork` class.

- **Contrastive Loss**: The training of the Siamese network is guided by the contrastive loss, defined in the `ContrastiveLoss` class. This loss function encourages the network to minimize the distance between images from the same person while maximizing the distance between images from different people.

- **Custom Dataloader**: The project uses the Olivetti Faces dataset, which is loaded and preprocessed by the `OlivettiFaces` class. It prepares pairs of face images with labels (0 for the same person, 1 for different people) for training and evaluation.

- **Training Loop**: The training loop trains the Siamese network using the prepared dataset. It optimizes the model using the Adam optimizer and records the loss history.
 
## Technology Stack

* Pytorch
* Numpy
* Torchvision
* Scikit learn
* Matplotlib

## Result

Our model produced an accuracy of 95.5% .
![Sample Outputs](https://github.com/Coolsheru2526/Face-Recognition/blob/main/outputs.jpg?raw=true)
