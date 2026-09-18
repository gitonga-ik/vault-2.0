A neural network is a machine learning model that stacks simple "neurons" in layers and learns pattern-recognizing weights and biases from data to map inputs to outputs.

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


# References
- [IBM](https://www.ibm.com/think/topics/neural-networks)