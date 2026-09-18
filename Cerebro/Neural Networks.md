A neural network is a machine learning model that stacks simple "neurons" in layers and learns pattern-recognizing weights and biases from data to map inputs to outputs.

# High level structure of a neural network 
At a high level, the structure of the neural network is as follows:
- **Input Layer:** Receives raw data, such as pixels from a picture or numbers from a spreadsheet.
- **Hidden Layers:** Perform math calculations between the input and output layers to find hidden patterns.
- **Output Layer:** Gives the final answer, choice, or prediction.

![[Pasted image 20260918142101.png]]

This is an overly simplified way of thinking about it but it gives the general structure of the network.
# How do they work?
Neural networks work by processing the information from the input through multiple layers before giving a probability or a prediction for the intended output.

Earlier layers in a neural network process simple, low-level features and basic patterns directly from raw input data. Because these initial neurons have small, highly localized receptive fields (or examine tiny slices of data at a time), they act as fundamental building blocks that deeper layers build upon.

Deeper layers take the information from the earlier layers and combine it to come up with more complex signals. The final layer the aggregates all the complex components found by the middle layers to synthesize full objects, global context, and final predictions.

Taking the example of an image being analyzed, the first layer would receive the raw image represented as a matrix of numbers. For a color image, this would be a 3D grid of numbers corresponding to Width × Height × RGB Color Channels. The layer the  
# References
- [IBM](https://www.ibm.com/think/topics/neural-networks)