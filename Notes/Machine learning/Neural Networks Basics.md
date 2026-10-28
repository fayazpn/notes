# Neural Networks Basics

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Layered networks of weighted connections that learn complex, non-linear patterns via backpropagation.

## Key points

- A network = layers of neurons, each applying weights + a non-linear activation function (ReLU, sigmoid)
- Forward pass computes predictions; backpropagation computes gradients to update weights via gradient descent
- Loss function measures prediction error; the optimizer (SGD, Adam) uses gradients to reduce it
- Data needs depend on the task, model size, prior training, and regularization; compare with simpler baselines

## Practice

- [ ] Build a simple feedforward network for a classification task in a framework of your choice
- [ ] Explain forward pass vs backpropagation in your own words
- [ ] Compare training accuracy over epochs with and without dropout

## Related

- [[Notes/Machine learning/Supervised Learning Basics|Supervised Learning Basics]]
- [[Notes/Machine learning/Overfitting and Regularization|Overfitting and Regularization]]
- [[Notes/Machine learning/Deep Learning Frameworks|Deep Learning Frameworks]]
