# Gradient Descent and its types

**Gradient descent** is an optimization algorithm often used for finding the weights or coefficients of machine learning algorithms that minimize the error of the model. 

The goal is to continue to try different values for the coefficients, evaluate their model error and select new coefficients that have a slightly better \(lower\) error moving down along a gradient or slope or errors. Hence the name "**gradient descent**".

### Gradient Descent Procedure

**Step 1:** Start off with some random initial values for the coefficient\(s\) of the function.  
                               **coefficient = 0.0**

**Step 2:** Calculate the cost of the coefficient\(s\)  
                               **cost = f\(coefficient\)**  
                                           or  
                      **cost = evaluate\(f\(coefficient\)\)**

**Step 3:** Calculate the derivative of the cost. Derivatives gives the slope of the function which helps to determine the direction \(sign\) to move the coefficient values in order to get to a lower cost in the next iteration.  
                              **delta = derivative\(cost\)**  
  
**Step 4:** From the derivative, we know which direction is downhill. A learning rate parameter \(alpha\) must be specified that controls how much the coefficients can change on each update.  
                     **coefficient = coefficient – \(alpha \* delta\)**

**Step 5:** **Repeat** until the cost of the coefficient\(s\) is **0.0** or close to **zero**.

## 3 Types of Gradient Descent

### Stochastic Gradient Descent \(SGD\)

It is a variation of the gradient descent algorithm that:

* calculates the error for each example in the training dataset
* and updates the model immediately for each example

The frequent updates immediately give an insight into the performance of the model and the rate of improvement. 

But updating the model so frequently is more computationally expensive and takes significantly longer to train models on large dataset.

### Batch Gradient Descent

It is a variation of the gradient descent algorithm that:

* calculates the error for each example in the training dataset
* but only updates the model after all training examples have been evaluated

**Note:** One cycle through the entire training dataset is called a training epoch.

Fewer updates to the model means this variant of gradient descent is more computationally efficient than stochastic gradient descent. Model updates, and in turn training speed, may become very slow for large datasets.

### Mini-Batch Gradient Descent

It is a variation of the gradient descent algorithm that:

* calculates the error by splitting the training dataset into small batches
* and update model coefficients after each batch
* Most common implementation of gradient descent since it finds a balance between the other two variations of gradient descents and avoids local minima

Mini-batch requires the configuration of an additional “mini-batch size” hyperparameter for the learning algorithm.

Link:  
- MachineLearningMastery: [Gradient Descent for ML](https://machinelearningmastery.com/gradient-descent-for-machine-learning/)  
- MachineLearningMastery: [Types of Gradient Descent](https://machinelearningmastery.com/gentle-introduction-mini-batch-gradient-descent-configure-batch-size/)

