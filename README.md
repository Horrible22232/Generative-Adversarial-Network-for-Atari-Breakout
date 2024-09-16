# Generative Adversarial Network for Atari Breakout

## Introduction

In recent years, Generative Adversarial Networks (GANs) have become a widely known and important subfield of Machine Learning. GANs are unsupervised learning algorithms for generating images, which means that unlabeled data in the form of images is needed in order to generate new, unseen images from a data distribution.

## Details

A Generative Adversarial Network consists of two parts, namely the generator and the discriminator. The discriminator is trained to determine if a sample belongs to the generated or the real dataset. On the other hand, the generator tries to fool the discriminator by generating images that are similar to the real data. While training, the generator becomes better at generating, and the discriminator becomes better at identifying generated images. Overall, GANs are a powerful method to approximate complex data distributions.

## Try it out!

It is strongly recommended to try out the code yourself by following these instructions:

1. Visit [Google Colab](https://colab.research.google.com/)
2. Upload or open `GAN.ipynb` in Colab
3. Select a GPU for faster training (Runtime => Change runtime type => Hardware accelerator = GPU => Save)
4. Run each cell in `GAN.ipynb`

## Approach

![GAN Output](https://raw.githubusercontent.com/Horrible22232/Generative-Adversarial-Network/master/imgs/GAN-Output.png "GAN-Output.png")

This implementation of a Generative Adversarial Network shows how GANs can be used to successfully generate Atari images by using PyTorch and OpenAI gym. First of all, training a GAN is hard. Models often collapse or don't converge. In this implementation, we use the standard GAN framework with some techniques to improve training stability.

**Generator Architecture**

The generator converts random noise vectors from a latent space into images resembling Breakout game frames:

- **Input**: A noise vector of size 100.
- **Linear Layer**: Expands the noise vector into a higher-dimensional space.
- **Convolutional Blocks**: Uses upsampling and convolutions to progressively increase the spatial resolution.
- **Output**: A `Tanh` activation maps pixel values to `[-1, 1]` to match the normalized image range.

**Discriminator Architecture**

The discriminator identifies whether an image is real or generated:

- **Convolutional Blocks**: Downsample input images using convolutions with `LeakyReLU` activations to extract features.
- **Flatten and Output**: A final linear layer outputs a single scalar value indicating authenticity.

**Training Details**

- **Loss Function**: Binary Cross-Entropy with Logits Loss (`BCEWithLogitsLoss`) to improve stability by combining a sigmoid layer with binary cross-entropy loss.
- **Optimizers**: Both networks use the Adam optimizer with a learning rate of `2e-4` and betas `(0.5, 0.999)`.
- **Data Preparation**: Collects frames from the Breakout-v4 environment, normalizing them to `[-1, 1]`.
- **Visualization**: After each epoch, a real and a generated image are displayed side by side to show the generator's progress.

## References

[1] Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron C. Courville, Yoshua Bengio: **Generative Adversarial Networks**. CoRR abs/1406.2661 (2014)
