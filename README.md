# Cartoon World
 ## -A simple cartoonizer able to turn your images or videos to cartoons using the power of GANs and Vgg16 NN archticture



### -FLOWCHART OF WHITE-BOX-CARTOONIZATION MODEL :


<img align= center height=450px src=https://user-images.githubusercontent.com/75990647/192298994-d80bb374-568c-4906-a10b-75958a3f9c1f.png>

### ARCHITECTURE OF WBC MODEL:

<img align= center height=350px src=https://user-images.githubusercontent.com/75990647/192300499-dfbe29b1-ea56-43b2-ab14-30564071f688.png>

<li>the architecture of the generator network and discriminator
network in the above ﬁgure. The generator network is a fully convolutional
U-Net-like network. I used convolution layers with stride2 for down-sample and
bilinear interpolation layers for upsampling to avoid checkerboard artefacts. The
network consists of only three kinds of layers: convolution, Leaky ReLU (LReLU) and
bilinear resize layers. This enables it to be easily embedded in edge devices such as
mobile phones. PatchGAN is adopted in the discriminator network, where the last
layer is a convolution layer. Each pixel in the output feature map corresponds to a
patch in the input image, with the patch size equals to the perceptive ﬁeld, and is
used to judge whether the patch belongs to cartoon images or generated images.
PatchGAN enhances the discriminative ability of details and accelerates training.
Spectral normalization is placed after every convolution layer (except the last one)
to enforce Lipschitz constrain on the network and stabilize training.</li>


### METHODOLOGY :
 <ul><li> INTRODUCTION TO GENERATIVE ADVERSARIAL NETWORKS (GANs) </li></ul>
 <ul><ul>
 <li>Generative adversarial networks (GANs) are an exciting recent innovation in
machine learning. GANs are generative models: they create new data instances that
resemble your training data. For example, GANs can create images that look like
photographs of human faces, even though the faces don't belong to any real
person.</li>

 <li>Generative Adversarial Networks, or GANs for short, are an approach to
generative modelling using deep learning methods, such as convolutional neural
networks. Generative modelling is an unsupervised learning task in machine
learning that involves automatically discovering and learning the regularities or
patterns in input data in such a way that the model can be used to generate or
output new examples that plausibly could have been drawn from the original
dataset.</li>

 <li>GANs are a clever way of training a generative model by framing the problem
as a supervised learning problem with two sub-models: the generator model that
we train to generate new examples, and the discriminator model that tries to
classify examples as either real (from the domain) or fake (generated). The two
models are trained together in a zero-sum game, adversarial, until the discriminator
model is fooled about half the time, meaning the generator model is generating
plausible examples.</li>

 <li>GANs are an exciting and rapidly changing ﬁeld, delivering on the promise of
generative models in their ability to generate realistic examples across a range of
problem domains, most notably in image-to-image translation tasks such as
translating photos of summer to winter or day to night, and in generating
photorealistic photos of objects, scenes, and people that even humans cannot tell
are fake.</li>
 </ul></ul>
 
 <ul><li> DEEP CONVOLUTIONAL GENERATIVE ADVERSARIAL NETWORKS (DCGAN) :</li></ul>
 
 <ul><ul>
 <li>The deep convolutional generative adversarial network, or DCGAN for short,
is an extension of the GAN architecture for using deep convolutional neural
networks for both the generator and discriminator models and conﬁgurations for
the models and training that result in the stable training of a generator model.</li>
 
 <li>The DCGAN is important because it suggested the constraints on the model
required to e ectively develop high-quality generator models in practice. This
architecture, in turn, provided the basis for the rapid development of a large number
of GAN extensions and applications.</li>
 
 </ul></ul>
 
 <ul><li> ARCHITECTURE OF GAN </li><ul>
 <ul><ul>
 <li>The architecture of a GAN has two basic elements: the generator network
and the discriminator network. Each network can be any neural network, such as an
Artiﬁcial Neural Network (ANN), a Convolutional Neural Network (CNN), a
Recurrent Neural Network (RNN), or a Long Short Term Memory (LSTM). The
discriminator has to have fully connected layers with a classiﬁer at the end.</li>
  
<li> A generative adversarial network (GAN) has two parts:<li>
  <ul>
   <li>The generator learns to generate plausible data. The generated instances become negative training examples for the discriminator.</li>
   <li>The discriminator learns to distinguish the generator's fake data from real data. The discriminator penalizes the generator for producing implausible results </li>
  </ul>
  
  
 </ul></ul>
 
