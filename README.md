# PokeGan
Generating Pokemon with a Deep Convolution Generative Adversarial Network.

## Dataset
Original images:

- [Pokemon](https://s3.amazonaws.com/syaffers-stuff/datasets/pokemon-sprites.tar.gz)

## Generative Adversarial Network (GAN)
GAN consist of two network:

 - A discriminator D receive input from training data and generated data. Its job is to learn how to distinguish between these two inputs.
 - A generator G generate samples from a random noise Z. Generator objective is to generate sample that is as real as possible it could not be distinguished by Discriminator.

### Deep Convolution GAN (DCGAN)
In DCGAN architecture, the discriminator `D` is Convolutional Neural Networks (CNN) that applies a lot of filters to extract various features from an image. The discriminator network will be trained to discriminate between the original and generated image. The process of convolution is shown in the illustration below:  
![](http://deeplearning.net/software/theano_versions/dev/_images/same_padding_no_strides_transposed.gif)


The generator `G`, which is trained to generate image to fool the discriminator, is trained to generate image from a random input. In DCGAN architecture, the generator is represented by convolution networks that upsample the input. The goal is to process the small input and make an output that is bigger than the input. It works by expanding the input to have zero in-between and then do the convolution process over this expanded area. The convolution over this area will result in larger input for the next layer. The process of upsampling is shown below:  
![](http://deeplearning.net/software/theano_versions/dev/_images/padding_strides_transposed.gif)

There are many name for this upsample process: full convolution, in-network upsampling, fractionally-strided convolution, deconvolution, or transposed convolution. 


## Training output
I have only trained this GAN for a few hours on [Google Colab](https://colab.research.google.com/). If you have access to high-level computing power, you can train longer to get better results.
- About 500 Epochs
![](./Gan.gif)
