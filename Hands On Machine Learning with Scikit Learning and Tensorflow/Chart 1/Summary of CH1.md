## What is machine learning?

&emsp; A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance on T, as measured by P, improves with experience E.  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&mdash;Tom Mitchell, 1997  

## Machine Learning is great for:
* Problems for which existing solutions require a lot of hand-tuning or long lists of rules: one Machine Learning algorithm can often simplify code and perform better.  
* Complex problems for which there is no good solution at all using a traditional approach: the best Machine Learning  techniques can find a solution.  
* Fluctuating environments: a Machine Learning system can adapt to new data.
* Getting insights about complex problems and large amounts of data.  

## Types of Machine Learning Systems  
* Supervised Learning:  
&emsp; A typical supervised learning task are classification and regression.  
    * K-Nearest Neighbors  
    * Regression  
    * Support Vector Machines (SVMs)  
    * Decision Trees and Random Forests  
    * Neural networks (Note that some neural network architectures can be unsupervised or semisupervised.)  
* Unsupervised Learning:
    * Clustering  
        * k-Means  
        * Hierarchical Cluster Analysis (HCA)  
        * Expextation Maximization  
    * Visualization and dimensionality reduction  
        * Principal Component Analysis (PCA)  
        * Kernel PCA  
        * Locally-Linear Embedding (LLE)  
        * t-distributed Stochastic Neighbor Embedding (t-SNE)  
    * Association rule learning  
        * Aprior  
        * Eclat  
* Semisupervised Learning
    * Deep belief networks (DBNs)  
* Reinforcement Learning  
    * Deep Q netowrk (DQN)  
## Batch and Online Learning  
* Batch learning  
&emsp;In *batch learning*, the system is incapable of learning incrementally: it must be trained using all the available data. This will generally take a lot of time and computing resources, so it is typically done offline.  
* Online learning (Stochastic learning)  
&emsp;In online learning, you train the system increnentally by feeding it data instances sequentially, either individually or by small groups called *mini-batched*. One important parameter of online learning systems is how fast they should adapt to changing data: this is called the *learning rate*.  
&emsp;A big challenge with online learning is that if bad data is fed to the system, the system's performance will gradually decline. To reduce this risk, you need to monitor your system closely and promptly switch learning off (and possibly revert to a previously working state) if you detect a drop in performance. You may also want to monitor the input data and react to abnormal data.  

## Instance-Based v.s. Model-Based Learning  
* Instance-based learning  
&emsp;This is called *instance-based learning*: the system learns the examples by heart, then generalizes to new cases using a similarity measure.  
* Model-based learning  
&emsp; Another way to generalize from a set of examples is to build a model of these examples, then use that model to make *predictions*. This is called *model-based learning*.  

## Main challenges of Machine Learning  
* __Insufficient Quantity of Training Data__  
&emsp;For most machine learning algorithms, it takes a lot of data to work properly. Even for very simple problems you typically need thousands of examples, and for complex problems such as image or speech recognition you may need millions of examples.  
    * __Futher reading__:  
        * [Scaling to Very Very Large Corpora for Natural Language Disambiguation](http://www.aclweb.org/anthology/P01-1005)  
        * [The Unreasonable Effectiveness of Data](https://static.googleusercontent.com/media/research.google.com/zh-TW//pubs/archive/35179.pdf)  
* __Nonrepresentative Training Data__  
&emps;In order to generalize well, it is crucial that you training data be representative of the new cases you want to generalize to. By using a nonpresentative training set, we trained a model that unlikely to make accurate predictions. It is crucial to use a training set that is representative of the cases you want to generalize to. This is often harder than it sounds: if the sample is too small, you will have sampling noise, but even very large samples can be nonrepresentative if the sampling method is flawed. This is called sampling bias.  

* __Poor-Quality Data__  
&emsp;If your training data is full of errors, outliers, and noise, it will make it harder for the system to detect the underlying patterns, so your system is less likely to perform well. It is often well worth the effort to spend time cleaning up your tranining data.  

* __Irrelevant Features__  
&emsp; Your system will only be capable of learning if the training data contains enough relevant features and not too many irrelevant ones. A critical part of the success of a machine learning project is coming up with a good set of features to train on. This process, called *feature engineering*, involves:  
    * *Feature selection*:  
    selecting the most useful features to train on among existing features.  
    * *Feature extraction*:  
    combining existing features to produce a more useful one.  
    * Creating new features by gathering new data.  

* __Overfitting the Training Data__  
&emsp;In machine learning this is called *overfitting*: it means that the model performs well on the training data, but it does not generalize well. Overfitting happens when the model is too complex relative to the amount and noisiness of the training data. The possible solutions are:  
    * To simplify the model by selecting one with fewer parameters, by reducing the number of attributes in the training data or by      constraining the model.  
    * To gather more training data.  
    * To reduce the noise in the training data.  

&emsp;&emsp;&emsp;Constraining a model to make it simpler and reduce the risk of overfitting is called *regularization*. The amount of regularization to apply during learning can be controlled by *hyperparameter*. Tuning hyperparameters is an important part of building a machine learning system.  

* __Underfitting the Training Data__  
&emsp;*Underfitting* is the opposite of overfitting: it occurs when your model is too simple to learn the underlying structure of the data.  The main options to fix this problem are:  
    * Selecting a more powerful model, with more parameters.  
    * Feeding better features to the learning algorithm.  
    * Reducing the constraints on the model.  
                                           
## Testing and Validating  
&emsp;The only way to know how well a model will generalize to new cases is to actually try it out on new cases. Therefore we split data into three sets: the *training* set, *test* set and *validation* set. We train multiple models with various hyperparameters using the training set, select the model and hyperparameters that perform best on validation set and get an estimate of the generalization error by test set.  
* *why we need test set and validation set?*  
These data set help us to evaluate our model. The test set can give us the out-of-sample error, this value tells us how well your model will perform on instances it has never seen before. By this reason, we can't test the model and select the hyperparameters on test set simltaneously. So the validation set comes in handy.  
*  *How to split the training set, test set and validation set?*  
In usually, we use the 80% of the data for training and hold out 20% for testing. To avoid wasting too much training data in validation sets, a common technique is to use *cross-validation*: the training set is split into complementary subsets, and each model is trained against a different combination of these subsets and validated against the remaining parts.  

## No Free Lunch Theorem  
&emsp;A model is a simplified version of the observations. The simplifications are meant to discard the superfluous details that are unlikely to generalize to new instances. However, to decide what data to discard and what data to keep, you must make *assumptions*. In a famous 1996 paper, David Wolpert demonstrated that if you make absolutely no assumption about data, then there is no reason to prefer one model over any other. This is called the *No Free Lunch (NFL)* theorem.  
* __Futher read__:  
    * [The Lack of A Priori Distinctions Between Learning Algorithms](https://sci-hub.tw/https://www.mitpressjournals.org/doi/10.1162/neco.1996.8.7.1341)
