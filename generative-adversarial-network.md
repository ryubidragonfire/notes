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

## Video
Ian Goodfellow: https://www.youtube.com/watch?v=HN9NRhm9waY
- training: 2:00 - 5:00
- DCGAN generative model good for generating small images from a specific domain.
- Vector Space Arithmatic: 
  - man with glasses - man + women -> women with glasses (need to decode into pixel values)
  - word embedding (no need to decode)
- Mode Collapse
  - related to Game Theory
  - OK when: max discriminator, then min generator
  - Fail is the other round
  - Generator generates several exact copies of images
  - partial fix by added nearest-neighbour features constructed from current mini-batch to the discriminator: **minibatch GAN** 
- Struggle with 1000 classes
- Convolutional network can count ??!!
## Applications
- **Text to Image**: 
  - GAN take *text description of the image* as additional input
  - ***descriminator*** will descriminate the image generated, and the appropriateness of the text description
  - lack diversity in the images generated based on given text
  - Generate pokemon (see youtube - Yota Ishida)
  - Super-resolution
  - ?? music generation ??
  - !! https://www.youtube.com/watch?v=rTawFwUvnLE
  - iGAN: draw simple lines, generate texture and colour
  - Introspective Adversarial Networks
  
 ## GAN
 - ***generative model*** based on supervised learning + game theory
 - learn to generate realistic samples
 - to improve: currently leaning to minimise the cost function, but not to reach equilibrium.
 - speech synthesis (e.g. wavenet: currently sequential process)
 - video generator (with wavenet)
 - can be used in data compression? bi-directional GAN
 
 ## Video on practicalities when training
 - https://www.youtube.com/watch?v=X1mUN6dD8uE
 
