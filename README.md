# FLMM
FLMM

The FLNN is a type of neural network that is inspired by fluid dynamics and lattice Boltzmann methods. It uses a lattice structure to organize the neurons and their connections.

Here's a breakdown of the main components and operations in the FLNN implementation:

Class Definition:

The FluidLatticeNeuralNetwork class encapsulates the FLNN implementation.
It takes two parameters during initialization: layerSizes and learningRate.
layerSizes is a vector that specifies the number of neurons in each layer of the network.
learningRate controls the rate at which the network adjusts its weights during training.
Initialization:

The initializeWeights function initializes the weights of the FLNN.
It creates a 3D vector weights to store the weights between neurons.
The weights are randomly initialized using a normal distribution.
The initialization process follows the Xavier initialization approach, where the weights are scaled based on the number of neurons in the previous layer.
Forward Propagation:

The predict function takes an input vector and propagates it forward through the FLNN to generate predictions.
It initializes the activations vector with the input values.
For each layer, it calculates a weighted sum of the activations from the previous layer using the weights.
The weighted sum is passed through the activation function (ReLU) to obtain the new activations for the current layer.
The process is repeated for each layer until the output layer is reached.
The final activations at the output layer are returned as predictions.
Backpropagation and Training:

The train function trains the FLNN using a supervised learning approach.
It takes a set of input-target pairs (inputs and targets) and the number of training epochs.
During each epoch, the function iterates through the input-target pairs and performs the following steps:
Forward propagation: The input is fed through the network, and the predicted output is obtained.
Error calculation: The error between the predicted output and the target output is calculated.
Backpropagation: The error is propagated backward through the network to update the weights.
The errors at each layer are calculated based on the errors from the previous layer.
The weights are updated using the calculated errors, the learning rate, and the activation derivatives.
Regularization is applied to prevent overfitting by penalizing large weights.
The total error for the epoch is accumulated.
After each epoch, the trained weights are saved to a file.
The process is repeated for the specified number of epochs.
File I/O:

The loadWeightsFromFile function allows loading pre-trained weights from a file.
The saveWeightsToFile function saves the trained weights to a file.
Activation Function and Derivative:

The FLNN uses the rectified linear unit (ReLU) as the activation function.
ReLU returns the input value if it is positive, and 0 otherwise.
The activationFunction function implements ReLU.
The activationDerivative function returns the derivative of ReLU, which is 1 for positive values and 0 for negative values.
Error Calculation:

The calculateError function calculates the mean squared error between the predicted output and the target output.
It sums the squared differences between corresponding elements in the predicted and target vectors and divides by 2.
Example Usage:

After training the FLNN, the example usage section demonstrates how to use the trained network.
It calls the predict function with a sample input vector to obtain the predicted output.
The predicted output is printed to the console.
That's a summary of the FLNN implementation. The FLNN combines concepts from fluid dynamics, lattice Boltzmann methods, and neural networks to create a unique architecture for solving machine learning problems.
