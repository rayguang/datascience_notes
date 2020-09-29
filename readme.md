### Bias vs Variance

### Overfitting and Underfitting


### Regularization L1 vs L2
[L1 vs L2](https://explained.ai/regularization/L1vsL2.html#:~:text=From%20a%20practical%20standpoint%2C%20L1,you%20have%20collinear%2Fcodependent%20features.)

### SVM



### What is p-value
p-value is the probabiity given the null hypothesis is true, what is the probability that we observe the sample results:  P( P(what we observed from the sample ) | H0 is true)

a is significance level, 

if p < a, reject the null H0;

if p > a, failed to reject the null H0

### What is training set, validation set and test set
```for each epoch
    for each training data instance
        propagate error through the network
        adjust the weights
        calculate the accuracy over training data
    for each validation data instance
        calculate the accuracy over the validation data
    if the threshold validation accuracy is met
        exit training
    else
        continue training
 ```
 
**Training Set**: this data set is used to adjust the weights on the neural network.

**Validation Set**: this data set is used to minimize overfitting. You're not adjusting the weights of the network with this data set, you're just verifying that any increase in accuracy over the training data set actually yields an increase in accuracy over a data set that has not been shown to the network before, or at least the network hasn't trained on it (i.e. validation data set). If the accuracy over the training data set increases, but the accuracy over the validation data set stays the same or decreases, then you're overfitting your neural network and you should stop training.

**Testing Set**: this data set is used only for testing the final solution in order to confirm the actual predictive power of the network.
