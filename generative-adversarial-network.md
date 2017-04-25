https://en.wikipedia.org/wiki/Generative_adversarial_networks
- type of artificial intelligence algorithms used in unsupervised machine learning, implemented by a system of two neural networks competing against each other in a zero-sum game framework.
  - https://en.wikipedia.org/wiki/Generative_model
    -  a ***generative model*** is a model for randomly generating observable data values, typically given some hidden parameters. It specifies a **joint probability distribution** over observation and label sequences. 
    - are used in machine learning for either ***modeling data directly*** (i.e., modeling observations drawn from a probability density function), or as an **intermediate step to forming a conditional probability density function**. A conditional distribution can be formed from a generative model through Bayes' rule.
  - https://en.wikipedia.org/wiki/Discriminative_model
    - a ***discriminative model***, also called ***conditional models***, are a class of models used in machine learning for **modeling the dependence of an unobserved variable *y* on an observed variable *x***. Within a probabilistic framework, this is done by modeling the conditional probability distribution P(y|x)} P(y|x), which can be used for predicting ***y*** from ***x***.
    - ***Discriminative models***, as opposed to ***generative models***, do not allow one to generate samples from the joint distribution of  ***x*** and ***y***. 

- One network is *generative* and one is *discriminative*.[1] 
  - The ***generative network*** is taught to map from a **latent space** to a particular data distribution of interest.
  - The ***discriminative network*** is simultaneously taught to discriminate between instances from the **true data distribution** and **synthesized instances** produced by the generator. 
  - The *generative network's* training objective is to **increase the error rate of the *discriminative network*** (i.e., "fool" the ***discriminator network*** by producing novel synthesized instances that appear to have come from the true data distribution). 
## In practice
- A particular dataset serves as the training data for the discriminator. 
- **Training** the ***discriminator*** involves presenting the discriminator with **samples from the dataset** and **samples synthesized by the *generator***, and **backpropagating from a binary classification loss**. 
- In order to produce a sample, typically the ***generator*** is seeded with a **randomized input that is sampled from a predefined latent space** (e.g., a multivariate normal distribution). Training the ***generator*** involves **back-propagating the negation of the binary classification loss of the discriminator**. The ***generator* adjusts its parameters** so that the **training data** and **generated data cannot be distinguished by the *discriminator* model**. The goal is to find a setting of parameters that makes generated data look like the training data to the discriminator network.[4] 
- The ***generator*** is typically a **deconvolutional neural network**, and the ***discriminator*** is a **convolutional neural network**.
