# Image-Generation-Using-VQVAE
## Overview of VQVAE Structure 
VQ-VAE is a type of variational autoencoder that uses vector quantisation to obtain a discrete latent representation. It differs from VAEs in two key ways: 
-  Encoder network outputs discrete, rather than continuous, codes.
-  A prior is learnt rather than static. 

In order to learn a discrete latent representation, ideas from vector quantisation (VQ) are incorporated. Using the VQ method allows the model to circumvent issues of posterior collapse - where the latents are ignored when they are paired with a powerful autoregressive decoder - typically observed in the VAE framework. Pairing these representations with an autoregressive prior, the model can generate high quality images, videos, and speech as well as doing high quality speaker conversion and unsupervised learning of phonemes.

### VQVAE-MODEL
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/assests/vqvae.png" width="600" height="200">

### QUANTIZATION MODULE
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/assests/Vector%20Quantization%20module.png" width="600" height="300">

## Training process 

 - Initially VQVAE is trained to learn discreate features from the images through a Image recontruction task.
 - Later we collect all the Discreate latent codes and train a prior ontop of these latent codes.
 - Here we choose gpt as our prior model which will predict the next tokens based on the previously predicted tokens.
 
### Discreate Latent Code from Trained VQVAE:
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/assests/prior.png" width="450" height="500">

### Training GPT prior with future token prediction task:
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/assests/prior2.png" width="450" height="500">

## Reconstructions of VQVAE Model
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/reconstructions/reconstructions-8.jpeg" width="500" height="500">
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/reconstructions/reconstructions-7.jpeg" width="500" height="500">

## Generated Images using Trained vqvae decoder and GPT prior
<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/generations/generations-1.jpeg" width="300" height="300">  <img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/generations/generations-3.jpeg" width="300" height="300"> 

<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/generations/generations-6.jpeg" width="300" height="300">  <img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/generations/generations-4.jpeg" width="300" height="300"> 

<img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/generations/generations-11.jpeg" width="300" height="300">  <img src="https://github.com/BhanuPrakashPebbeti/Image-Generation-Using-VQVAE/blob/main/generations/generations-9.jpeg" width="300" height="300">
