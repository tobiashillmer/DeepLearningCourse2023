Exercise Sheet Deep Learning
Part2: Generative Models
Summer 23
This sheet includes a theoretical part and a practical assignment of the first part of the
lecture Deep Learning (Foundations). It should be handed in as pdf in groups of three via
ekvv-Moodle until 20.4.23. at 10.a.m (sharp). Please include a link to the code (e.g. Colab)
name1: Tobias Hillmer
name2: Lukas Schubert
name3: Yasar Plückebaum

PARTI – THEORY: For the following, you might answer only YES/NO (or abstain),
or you can add short arguments (at most two lines per question). If you are not sure, it is
better to abstain

1. Training the following generative models relies on the principle . . .
- maximizing the likelihood for observed data for restricted Boltzmann machines -> YES
- reconstruction error of given data for a variational auto-encoder -> NO, but reconstruction error with kl divergence or ELBO
- the direct log likelihood for normalizing flow models -> YES
- the direct log-likelihood for diffusion models -> NO

2. The following constraints need to hold for the neural architectures used in . . .
- diffusion models: invertibility of the implemented function ->NO
- variational autoencoder: output of the model needs to be low dimensional -> NO
- GAN: the discriminator has input dimension n, the dimension of the data to be generated -> YES
- normalizing flow: dimensionality stays the same -> YES

3. The following are trainable model parts/parameters of the models . . .
- GAN: generator is trainable, discriminator is fixed -> NO
- normalizing flow: forward mapping and its approximate inverse mapping -> NO, the mapping is exact
- VAE: all trainable parts are encoder and decoder functions, the probabilistic embedding is trained using sampling -> YES (however the embedding is not explicitly trained but only the encoder (via the reparametrization trick) and decoder)
- diffusion model: forward and backward mapping are trained -> NO

4. The following holds for GAN variants:
- WGAN optimizes a cost function which is given by the Kullback-Leibler divergence as measures for the difference of distributions -> NO, but given by the Wasserstein distance
- WGAN CT aims for a Lipschitz continuous discriminator -> YES
- conditional GAN uses a factorized latent space for generating data, where the factors correspond to classes -> No, the random noise is simply concatenated with an encoding of the conditioning, which results in the latent space
- BigGAN provides a text generation module -> NO, it generates images

5. The following tasks can be addressed by . . .
- Domain adaptation: Cycle GAN -> YES
- Diffusion models: to approximate a highly nonlinear probability distribution where sampling is particularly efficient -> NO, sampling is inefficient
- Guided diffusion to generate images from labels or signals such as text -> YES
- VAE to have an explicit analytic description of a high dimensional and nonlinear probability distribution -> NO, the description is not explicit and analytic

PARTII – PRACTICE: You can use code and models which are publicly available,
please clearly reference all sources and tools. Please give a link to your code (e.g. colab).
The length of the answer is limited to one page in total for the description of both parts
including images. Please provide: short description what you did, how it is done, what is
the result. Please be prepared to present the solution in the exercises.

1. Take the Fashion MNIST data set and train a variational autoencoder (VAE) on these
data. Provide some insight in how good the data are represented, e.g. by reporting
the reconstruction error and displaying typical results of generated images. What
happens if you interpolate in between two points in the latent space for the respective
encoded data points? Display examples within a class and in between two different
classes.


2. Use any other generative model and train it using the Fashion MNIST data. Describe
how it is trained and the result.

