# Generative-Adversarial-Network

On progress

# Introduction
In recent years, Generative Adversarial Networks (GANs) have become a widely known and important subfield of Machine Learning. GANs are unsupervised learning algorithms for generating images, so unlabled data in form of images is needed in order to generate new, unseen images from a data distribution.

# Details
A Generative Adversarial Network consists of two parts, namely the generator and predictor. The predictor is trained to determine if a sample belongs to the generated or real data set. On the other hand, the generator tries to fool the discriminator by generating images, which are similar to the real data. 
In the course of training, the generator gets better in generating and the discriminator in identifying generated images. All in all, GANs are a powerful methode to approximate a data distribution.

# Try it out!
It is strongly recommended to try out the code by yourself by following this instructions: \
1. Visit https://colab.research.google.com/ \
2. Open GAN.ipynb \
3. Select a GPU for faster training (Runtime => Change runtime type => Hardware accelerator = GPU => save)\
4. Run GAN.ipynb

# Approach



# References
[1] Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron C. Courville, Yoshua Bengio: Generative Adversarial Networks. CoRR abs/1406.2661 (2014)\
[2] Martín Arjovsky, Soumith Chintala, Léon Bottou: Wasserstein GAN. CoRR abs/1701.07875 (2017)
