# Gettin' into the (Tensor)Flow!

by Piérre Reimertz

## Applied Machine Learning

How can we apply machine learning to our programs without creating an entire machine learning algorithm.

Example: What if we used machine learning to detect which hand a user was using to scroll and changed out UI's to better serve them? E.g. moving the hamburger menu from the left to the right based on handed-ness.

## TensorFlow.js

**Tensors**: Core data structure — turns data into something the robot can work with

**Operations**: Done on tensors and are immutable. Used to _manipulate_ and _combine_ data. E.g. Linear algebra, normalization, convultion, reduction, matrices.

**Models/Layers**: Think of it like the brain — it learns by accumulating knowledge and can be trained.

### Layers

There is always an input and an output layer. In the middle, there are hidden layers. Like a digital neuron.

Takes weighted inputs and a bias and runs it through an activation function — based on the values, should we _activate_ the neuron? Sigmoid and ReLU are the functions most used as they are closest to our own brain.

### Pre-trained brains

Tensorflow.js comes with some pre-trained "brains" that we can apply to common problems.

- Image classification
- Object detection
- Speech command recognition
- ...and more!
