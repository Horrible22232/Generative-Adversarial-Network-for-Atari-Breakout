# Generative-Adversarial-Network

# Introduction
In recent years, Generative Adversarial Networks (GANs) have become a widely known and important subfield of Machine Learning. GANs are unsupervised learning algorithms for generating images, which means that unlabled data in form of images is needed in order to generate new, unseen images from a data distribution.

# Details
A Generative Adversarial Network consists of two parts, namely the generator and discriminator. The discriminator is trained to determine if a sample belongs to the generated or the real data set. On the other hand, the generator tries to fool the discriminator by generating images which are similar to the real data. 
While training, the generator becomes better at generating and the discriminator becomes better at identifying generated images. All in all, GANs are a powerful method to approximate a data distribution.

# Try it out!
It is strongly recommended to try out the code by yourself by following these instructions: 
1. Visit https://colab.research.google.com/ 
2. Open GAN.ipynb 
3. Select a GPU for faster training (Runtime => Change runtime type => Hardware accelerator = GPU => save)
4. Run GAN.ipynb

# Approach
![alt text](https://raw.githubusercontent.com/Horrible22232/Generative-Adversarial-Network/master/imgs/GAN-Output.png "GAN-Output.png")
This implementation of a Generative Adversarial Network shows how GANs can be used to successfully generate Atari images by using PyTorch and OpenAI gym. First of all, training a GAN is hard. Models often collapse or don't converge. To avoid some problems concerning GANs, such as dying gradients, Wasserstein GAN(WGAN) is partially implemented here.
The only difference is the discriminator model which includes a sigmoid activation function as an ouput. I observed improvements relating the training speed and performance of the discriminator. The generator contains transposed convolutional and dense layers which aim to upsample the input that consists of noise to an Atari image. However, the discriminator is made up by stacked convolutional layers as well as final dense layers and trained to identify the fake images.
As a result, in every iteration a sample from the real and generated set is plotted in order to demonstrate the training progress of the generator.

# References
[1] Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron C. Courville, Yoshua Bengio: Generative Adversarial Networks. CoRR abs/1406.2661 (2014)\
[2] Martín Arjovsky, Soumith Chintala, Léon Bottou: Wasserstein GAN. CoRR abs/1701.07875 (2017)
