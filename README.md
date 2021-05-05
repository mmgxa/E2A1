# E2A1

## 1. What is a neural network neuron?
A neuron is a function that is intended to mimic the biological neuron present in brains. It receives an input, scales it according to a(n) (initially) random weight, adds a bias, and then passes the value through an activation function. The output of each neuron is used as an input for subsequent layers until we reach the last layer, in which the outputs are the output of the neural network itself.

## 2. What is the use of the learning rate?
The learning rate determined how much the gradient is to be scaled while updating the weights during backpropagation. The choice of learning rate (LR) affects how quickly we want our model to achieve the minimum error/loss. A larger LR means the model will reach convergence earlier. However, as we approach convergence, we want to reduce the LR so as not to ‘jump’ across the minima (i.e. prevent oscillating around the minima). Typically, optimizers use an adaptive learning rate while training the model.

## 3. How are weights initialized?
Weights are ‘randomly’ initialized from a normal distribution - albeit with small numbers. They are weighted according to different parameters (e.g. in He initialization, the weights are multiplied with  <img src="https://render.githubusercontent.com/render/math?math=\sqrt(\frac{2}{n_{in}})">
 etc.). Researchers have done extensive studies on which type of initialization yields the best result according to the activation function.

Weights are not initialized with equal values (including 0 or any random value). This is because all the neurons will tend to ‘learn’ the same parameter, and the entire layer will behave like a single neuron. By having different values, we break the learning symmetry and yield a well-trained neural network.

A very nice visualization can be seen at https://www.deeplearning.ai/ai-notes/initialization/.


## 4. What is "loss" in a neural network?
The loss is the error between the actual (expected) output and the predicted (calculated) output. Ideally, when training is complete, the loss is 0. But during the training, the loss decreases as the neural network ‘learns’. The loss value is used to determine the gradients which in turn quantitatively describes how each weight in the previous layers need to be updated.

## 5. What is the "chain rule" in gradient flow?
The chain rule is used to compute derivatives of composite functions. Since we want to update the weights of the first layer, we need to update the weights of the last layer, then the second-last layer and so forth. The name ‘chain’ comes from the fact that the derivatives (intermediate) are linked (chained) together.
