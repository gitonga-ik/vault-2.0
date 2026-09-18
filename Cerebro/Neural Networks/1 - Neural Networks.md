A neural network is a machine learning model that stacks simple "neurons" in layers and learns pattern-recognizing weights and biases from data to map inputs to outputs.

*Vocubulary*
Percertron - The simplest type of artificial neuron, used in machine learning for [binary classification problems](https://deepai.org/machine-learning-glossary-and-terms/perceptron) (deciding if an input belongs to one of two groups). 
# High level structure of a neural network 
At a high level, the structure of the neural network is as follows:
- **Input layer**: holds the raw features  (X1,X2,X3,..) .  
- **Hidden layers**: consist of artificial neurons (or nodes) that transform inputs into new representations. Mathematically, hidden layers are expressed as the input features, multiplied by their associated weights and added bias to pass from one layer to the next layer, eventually arriving at the final output layer. This is where the **linear transformation** between input and output happens.   
- **Output layer**: After performing the linear transformation in the hidden layer, a nonlinear activation function (tanh, sigmoid, ReLU ) is added to produce the final prediction (such as a number for regression, or a probability distribution for classification).

![[Pasted image 20260918142101.png]]

This is an overly simplified way of thinking about it but it gives the general structure of the network.
# How do they work?
Neural networks work by processing the information from the input through multiple layers before giving a probability or a prediction for the intended output.

Earlier layers in a neural network process simple, low-level features and basic patterns directly from raw input data. Because these initial neurons have small, highly localized receptive fields (or examine tiny slices of data at a time), they act as fundamental building blocks that deeper layers build upon.

Deeper layers take the information from the earlier layers and combine it to come up with more complex signals. The final layer the aggregates all the complex components found by the middle layers to synthesize full objects, global context, and final predictions.

Taking the example of an image being analyzed, the first layer would receive the raw image represented as a matrix of numbers. For a color image, this would be a 3D grid of numbers corresponding to Width × Height × RGB Color Channels. The layer then passes these raw pixel values directly into the network without extracting features yet.

The middle layers would receive this information and begin combining the raw inputs to form more meaningful patterns. They would merge the basic line segments, color shifts, and edge maps identified by the initial transformations into intermediate representations such as textures, geometric shapes, and distinct object fragments like wheels, eyes, or handles. By processing broader regions of the image simultaneously, these layers successfully bridge the gap between simple pixel values and full visual entities.

The final layers would receive these assembled fragments and synthesize them into complete high-level concepts and decisions. They would aggregate the recognized components to evaluate the whole scene, identifying full objects and global contexts such as a complete car or an animal. Ultimately, these deep representations are flattened and passed to the output stage, which calculates the final probability scores to categorize what the image depicts.

# Training a neural network
Just like other machine learning algorithms, a neural net requires rigorous training to perform well on testing. To train a network, a single neuron computes: 

 z=∑i=1nwixi+b

 a=σ(z)

Where:

-  xi = input feature,
-  wi = weight,
-  b  = bias,
-  z  = weighted sum (linear transformation),
-  σ  = activation function (nonlinear transformation),
-  a  = output,

 σ  represents an activation function at the output layer that transforms the linear combination to fit the decision of the function. Using this architecture, the input features X are transformed into an output Y, serving as a predictive machine learning model.  

The power of a neural network comes from its ability to learn the right weights and biases from data. This is done by comparing the network’s prediction  Y^ to the true label  Y  and measuring the error using a [loss function](https://www.ibm.com/think/topics/loss-function). For example, in [classification](https://www.ibm.com/think/topics/classification-machine-learning) tasks, the loss might measure how far the predicted probability is from the correct answer.

To minimize this loss, the network uses an algorithm called [backpropagation](https://www.ibm.com/think/topics/backpropagation). The neural net trains in four steps:

- Forward pass: Inputs flow through the network, computing linear combinations, passing through the nonlinear activation function and producing an output prediction.  
- Error calculation: The loss function measures the difference between prediction and truth.  
- Backward pass (backpropagation): The error is propagated backward through the network. At each neuron, the algorithm calculates how much each weight and bias contributed to the error using the chain rule of calculus.  
- Weight update: The weights and biases are adjusted slightly in the direction that reduces the error, using an optimization method like [gradient descent](https://www.ibm.com/think/topics/gradient-descent).

![[Pasted image 20260918150908.png]]

This process is repeated many times over the training dataset. Each pass helps the network “tune” its internal parameters so that its predictions get incrementally closer to the correct answers. Over time, the network converges to a set of weights and biases that minimize error and generalize well to unseen data. Backpropagation, coupled with gradient descent, is the engine that makes neural networks work. It enables networks with millions (or even billions) of parameters to learn meaningful patterns from massive datasets.
# Types of Neural Networks
While multilayer perceptrons are the foundation, neural networks have evolved into specialized architectures suited for different domains:
- Convolutional neural networks (CNNs or convnets): Designed for grid-like data such as images. CNNs excel at image recognition, computer vision and facial recognition thanks to convolutional filters that detect spatial hierarchies of features.   
- [Recurrent neural networks (RNNs)](https://www.ibm.com/think/topics/recurrent-neural-networks): Incorporate feedback loops that allow information to persist across time steps. RNNs are well-suited for speech recognition, time series forecasting and sequential data.   
- Transformers: A modern architecture that replaced RNNs for many sequence tasks. Transformers leverage attention mechanisms to capture dependencies in natural language processing (NLP) and power state-of-the-art models like GPT.   
-  These variations highlight the versatility of neural networks. Regardless of architecture, all rely on the same principles: artificial neurons, nonlinear activations and optimization algorithms.

# References
- [IBM](https://www.ibm.com/think/topics/neural-networks)