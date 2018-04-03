The objective of this problem is to implement the AdaBoost algorithm. We will test the algorithm on handwritten digits from the USPS data set.

1. Implement the AdaBoost algorithm in R. The algorithm requires two auxiliary functions, to train and evaluate the weak learner. We also need a third function which implements the resulting boosting classifier. We will use decision stumps as weak learners, but a good implementation of the boosting algorithm should permit you to easily plug in arbitrary weak learners. To make sure that is possible, please use function calls of the following form:

• pars <- train(X, w, y) for the weak learner training routine, where X is a matrix the columns of which are the training vectors x(1) , . . . , x(n) , and w and y are vectors containing the weights and class labels. The output pars is a list which contains the parameters specifying the resulting classifier. (In our case, pars will be the triplet (j, θ, m) which specifies the decision stump).

• label <- classify(X, pars) for the classification routine, which evaluates the weak learner on X using the parametrization pars.

• A function c hat <- agg class(X, alpha, allPars) which evaluates the boosting classifier (“ag- gregated classifier”) on X. The argument alpha denotes the vector of voting weights and allPars contains the parameters of all weak learners.

2. Implement the functions train and classify for decision stumps. 2
   
3. Run your algorithm on the USPS data (the digit data we used in Homework 2, use the training and test data for the 3s and 8s) and evaluate your results using cross validation.
More precisely: Your AdaBoost algorithm returns a classifier that is a combination of B weak learners. Since it is an incremental algorithm, we can evaluate the AdaBoost at every iteration b by considering the sum up to the b-th weak learner. At each iteration, perform 5-fold cross validation to estimate the training and test error of the current classifier (that is, the errors measured on the cross validation training and test sets, respectively).

4. Plot the training error and the test error as a function of b.
