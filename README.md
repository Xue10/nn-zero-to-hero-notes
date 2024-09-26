# Neural Networks: Zero to Hero Notes
This is a note taking down points I think important for Andrej Karpathy's amazing course on neural networks.
Please correct me if I made any mistake in the notes.
## Lecture 1: Building micrograd
1. Introduce backpropagation
    
    Needs to know basic calculus

    Use backward function to calculate the gradients of variables 
2. Value class

    attributes:
    * data
    * gradient
    * _backward function 
    * _previous nodes and 
    * _operation done to get it

    functions:
    * for each math operation, you need a corresponding function with its _backward function
    * backward:
    
        build_topo: a function to recursively call to find all the previous nodes and return a list

        then for each nodes in reversed(topo), call its _backward function

3. Neuron class

    arguments 
    * number of inputs **nin**

    attributes:
    * a list of Value objects representing weights **w**
    * a Value objects representing bias **b**

    functions:
    * \_\_call__: how to calculate output

        **w * x + b**

        activation function
    * parameters
        return all the trainable parameters
4. Layer class
    
    _each neuron takes **nin** inputs and total number of neurons of the layer is **nout**_

    arguments
    * number of inputs
    * number of neurons/outputs

    attributes:
    * list of neurons
    
    functions:
    * \_\_call__

        output a list of Value objects
    * parameters
    
        return all the trainable parameters

5. MLP class

    arguments
    * number of inputs **nin**
    * list of intermediate and final number of outputs **nouts**

    attributes:
    * layer sizes(number of inputs and outputs)
    * list of layers

    functions:
    * \_\_call__

        output a list of Value objects
    * parameters
    
        return all the trainable parameters
6. Train
    * define loss function
    * training loop

        * forward
        * compute loss
        * zero grad
        * backward
        * step

To be continued
