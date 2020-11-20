### Bias vs Variance

### Overfitting and Underfitting


### Regularization L1 vs L2
[L1 vs L2](https://explained.ai/regularization/L1vsL2.html#:~:text=From%20a%20practical%20standpoint%2C%20L1,you%20have%20collinear%2Fcodependent%20features.)

### SVM

### K Nearest Neighbor
Four steps:
- Decide Distance metric
- Decide how many neighbors, odd number
- Weighted function, all neighbors same or not
- Local sensitivy hashing to find the neighbors in constant time

#### Cons:
- Cost lots of memory


### Random Forest
- bootstrap dataset D(subsampling with replacement) to m dataset, D1, ... Dm. D1 has the same size as D
- build classifier on each dataset, split the tree with k << d features, where k is set to sqrt(k). Decision tree will split all the way down (kind like overfitting)
- aggregate the results of all classifier
- prune: bottom up if the out of error rate does not improve, remove the tree

#### HPS for RFC:
- k, is set (no need to tune, set to sqrt(d))
- m, how many dataset, until you get bored

#### Pros:
- No need to preprocess data (e.g., scale of features not matter, cm vs m). Take care of missing data
- Less prone to overfit vs decision tree
- Explanability, e.g., feature selection
- Handle both categorical and continuous variables
- Fast
- No need for separate test dataset: out of bag error approx as if error from separate test set (1/3 of the D1 is used as out of bag sample). Train model on whole dateset, for free get unbiased estimator
- Robust for dealing with high dimensionality, good for feature selection
- Can "automatically" balance unbalanced dataset
- bias is not a function of ensemble size and is stable; variance tends to decrease as ensemble size increases. Bagging reduces variance! you can apply bagging to any algo, not only forest of trees.

#### Cons:
- Trees can be large, requires pruning
- Not super good for regression, no precise continuous nature prediction
- Predicitve model, not a descriptive tool: serve as a black-box, little control on what the model does (i.e., split the tree)
- Poor for image processing/classification, because pixel correlated and RFC treat each feature independently

#### Ref:
https://www.stat.berkeley.edu/~breiman/RandomForests/cc_home.htm

#### Misc:
strength vs correlation of trees, reduce m (number of features to split in each tree) reduces the correlation and the strengh and vice-versa. Therefore there is an optimal m value




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
