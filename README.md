This is all about GAN, its variants and some interesting projects with them. So.. let's start..

# Generative Adversarial Network
### in short : Generative Advarsarial Networks, GANs are a type of Neural Network Architecture that could generate real like data.
 
  GANs were introduced in 2014, by [Ian Goodfellow](https://www.linkedin.com/in/ian-goodfellow-b7187213/) and other researchers at the University of Montreal, including [Yoshua Bengio](https://www.linkedin.com/in/yoshuabengio) in their paper [Generative Adversarial Nets](https://arxiv.org/pdf/1406.2661.pdf).
  GAN is just an awesome idea, in which we simultaneously train two models, One aganist the other!!
  One of the models is called the **Generator**, the creator who 'generates' data and the other is called the **Discriminator**, who is trained to be an expert in distinguishing the real data from the fake. The whole story is about the Generator getting better and eventually generating real like data, thereby fooling the Discriminator by showing Fake(Generated) data and getting it certified as Real.

GANs’ potential is huge, because they can learn to mimic any distribution of data. That is, GANs can be taught to create worlds eerily similar to our own in any domain: images, music, speech, prose. They are robot artists in a sense, and their output is impressive..
And that must be why [Yann LeCun](https://www.linkedin.com/in/yann-lecun-0b999), Facebook's Chief AI Scientist reffered GAN, “the most interesting idea in the last 10 years in ML.”

You can read more in depth about GAN in this awesome [article from Analytics Vidhya](https://www.analyticsvidhya.com/blog/2017/06/introductory-generative-adversarial-networks-gans/).

And Let's move straight on to different variants of GANs! 

Moving directly to some Image generator GANs..we have..

## DCGAN
  DCGAN - Deep Convolutional GAN is an Image Generator Achitecture that uses a Transpose Convolutional Layer Network for Generating Images and a Covolutional Neural Network as Discriminator, a theory as simple as that.  
  In detail, The Discriminator is a Batch Normalized, Convolutional Neural Network(other than input layer) without Pooling and uses LeakyReLu activation for Input and Hidden Layers, and Sigmoid for the output layer. Also, due to the absence of Pooling Layers, It uses Convolutional Strides for down sampling the images.
  ![discriminator architecture](https://github.com/GokulDas027/Generative-Adversarial-Networks-GANs/blob/master/assets/dcgan_discriminator.png?raw=true)
