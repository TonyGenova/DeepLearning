## DeepLearning
Notes on Deep Learning/Neural Networks

Some from: https://www.youtube.com/watch?v=ysVOhBGykxs&t=1792s
 - that video also has python steps for an image classifier
 
 Good basic explanation: https://www.youtube.com/watch?v=ILsA4nyG7I0  
### Go back and finish: Good RNN explanation: https://www.youtube.com/watch?v=WCUNPb-5EYI
CNN writeup: http://cs231n.github.io/convolutional-networks/   
Looks like a great set of notes from the Stanford class: https://github.com/cs231n/cs231n.github.io  

Interesting notes on data pre-processing:  
http://cs231n.github.io/neural-networks-2/  

Interesting browser demos:
https://cs.stanford.edu/people/karpathy/convnetjs/

##### Types of Neural Networks
 - Feed Forward - data moves forward in calculation
 - Radial Basis Function - measures distance from center point
 - Recurrent Neural Networks - Hidden layer can send input backwards in layers
   - often used for sequential data
     - one output can work for next input
 - Convolutional Neural Networks - input data taken in batches, like a filter - picture data broken down, etc., then identified  
   - Most commonly applied to images

##### Data Structure
 - Tensors - basic unit of data - have a number of axes, shape, and data type
   - 0 Dimensional (1 piece of data): Scalar
   - 1 Dimensional (1 series of data): Vector
   - 2 Dimensional: Matrix
   - 3 Dimensional: Cube
   - 4 Dimensional: Series of Cubes

Neural Networks are optimized via __Backpropagation__, which starts and the output and uses the chain rule to get the derivative of each prior level (ie, the contribution to the loss function that that level provided). This is part of calculating the gradient descent as applied to the Neural Network.

##### Anatomy of a NN:  
 - Layers 
   - takes tensors as input, outputs tensors 
   - have weights applied to the input to produce the output
   - Different types for different data
     - Vector data - densely connected layers (Dense in Keras)
     - Sequence data (ie 3 dimensions, one is time) - recurrent layers (LSTM)
     - 4 dimension tensors - 2D Convolution Layers (Conv2D)
 - Input data 
 - Loss Function - Mean Sqaured Error for Regression problem, binary crossentrophy for binary classification problem, etc.  
 - Optimizer

##### Input Neurons
 - reads the raw input, sends information on it to hidden layers
   - usually a vector of input

##### Hidden Layer Neurons
 - Have weights and biases, interact between each other
 - So a first hidden layer will read all the input layers, with each neuron in the hidden layer having varying weights (-1 to 1) for each input layer
   - So, if have 3 inputs, second layer might have a neuron that weights them .1, .2, .3, and another neuron that weights them 1,0,-1, and so on, so the hidden layers will have varying combinations when weighting the input
 - Neuron in this layer will then be "squased" (sigmoid, RELU, etc below)
 - Output of first hidden layer can be input of second hidden layer, then third, etc
 
  
##### Activation Functions
 - Threshold Function - either 0 or 1 depending on threshold 
   - so, either fires or it doesn't
 - Sigmoid Function - 1/(1+e^x)
   - gives a continuous result between 0 and 1
 - RELU Function (Rectified Linear Unit) - Keeps positive result, otherwise 0
 - Hyperbolic Tangent Function - (1-e^-2x)/(1+e^-2x)  
   - continuous result between -1 and 1

##### Backpropogation
 - adjusts weights on each node to reduce error in output v specified target
   - Gradient Descent
     - Shortcut used in calculation: Change in weight/Change in error = Slope = derivative
 
##### Model Functions:   
Epochs: How many times to go over all the data    
batch size: size of samples to segment data into  
  
Training and Validation Loss: Chollet book p 74 shows good examples and visualization  
 
