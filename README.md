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
  In detail, The Discriminator is a Batch Normalized(except the input layer), Convolutional Neural Network without Pooling and uses LeakyReLu activation for Input and Hidden Layers, and Sigmoid for the output layer. Also, due to the absence of Pooling Layers, It uses Convolutional Strides for down sampling the images.
  ![discriminator architecture](https://github.com/GokulDas027/Generative-Adversarial-Networks-GANs/blob/master/assets/dcgan_discriminator.png?raw=true)

  The Generator Network consists of Batch Normalized(except the output layer) Transpose Covolutional Neural Network with ReLu activation for hidden layers and TanH as the activation function for the last layer. And it also uses strides 2, but this time for upsampling the initial image.
![generator architecture](https://github.com/GokulDas027/Generative-Adversarial-Networks-GANs/blob/master/assets/dcgan_generator.png?raw=true)

Take a look at the [Face Generator DCGAN model](https://github.com/GokulDas027/Generative-Adversarial-Networks-GANs/blob/master/Face_Generator.ipynb)

## Pix2Pix
  Pix2pix is a conditional generative adversarial network (cGAN) that learns mapping from an input image to an output image. It’s used for image-to-image translation i.e To transfer the features of one image to other image. 
  
  To train the discriminator, firstly the generator generates an output image and the discriminator looks at the input/target pair and the input/output pair and produces its guess about how realistic they are. The weights of the discriminator are then adjusted based on the classification error of the input/output pair and the input/target pair. The generator’s weights are then adjusted based on the output of the discriminator as well as the difference between the output and target image. 
  The generator consists of Encoder that converts the input image into a smaller feature representation, and Decoder, which looks like a typical generator, a series of transpose-convolution layers that reverse the actions of encoder layers. The discriminator, instead of identifying a single image as real or fake, will look at pairs of images (input image and unknown image that is either targete image or generated image), and output a label for pair as real or fake.
  
  The problem with pix2pix is training because the two image spaces are needed to be pre-formatted into a single X/Y image that held both tightly-correlated images.And if that seems to be a problem, lets try the next..

## CycleGAN
  CycleGAN is an even bigger architecture than the others, it is made of two discriminator, and two generator networks, using an Unsupervised approach i.e. the training images don’t have labels.
  The CycleGAN is also used for Image-to-Image translation and the objective is to train generators that learn to transform an image from domain 𝑋 into an image that looks like it belongs to domain 𝑌 (and vice versa).
  The Discriminator network is a similar Real or Fake, Convolutional classifier like that in DCGAN.
  ![discriminator architecture](https://github.com/GokulDas027/Generative-Adversarial-Networks-GANs/blob/master/assets/discriminator_layers.png?raw=true)
  
  While The Generators are made of an encoder, a conv net that is responsible for turning an image into a smaller feature representation, and a decoder, a transpose_conv net that is responsible for turning that representation into an transformed image. 
  
![generator architecture](https://github.com/GokulDas027/Generative-Adversarial-Networks-GANs/blob/master/assets/cyclegan_generator_ex.png?raw=true)
