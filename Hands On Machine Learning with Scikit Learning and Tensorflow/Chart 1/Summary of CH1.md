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
&emsp;In online learning, you train the system increnentally by feeding it data instances sequentially, either individually or by small groups called *mini-batched*. One important parameter of online learning systems is how fast they should adapt to changing data: this is called the *learning rate*. A big challenge with online learning is that if bad data is fed to the system, the system's performance will gradually decline. To reduce this risk, you need to monitor your system closely and promptly switch learning off (and possibly revert to a previously working state) if you detect a drop in performance. You may also want to monitor the input data and react to abnormal data.  


<pre><code>tell application "Foo"
    beep
end tell
</code></pre>                                               
