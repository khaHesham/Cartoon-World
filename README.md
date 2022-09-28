# Cartoon World
 ## -A cartoonizer able to turn your images or videos to HD cartoons using the power of GANs and Vgg16 NN archticture



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


### ----------------------- METHODOLOGY ----------------------- :
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
 
 <ul><li><strong> DEEP CONVOLUTIONAL GENERATIVE ADVERSARIAL NETWORKS (DCGAN) :</strong></li></ul>
 
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
 
 <ul><li><strong> ARCHITECTURE OF GAN </strong></li><ul>
 <ul><ul>
 <li>The architecture of a GAN has two basic elements: the generator network
and the discriminator network. Each network can be any neural network, such as an
Artiﬁcial Neural Network (ANN), a Convolutional Neural Network (CNN), a
Recurrent Neural Network (RNN), or a Long Short Term Memory (LSTM). The
discriminator has to have fully connected layers with a classiﬁer at the end.</li>
  
<li> A generative adversarial network (GAN) has two parts:<li>
  <ul>
   <li>The generator learns to generate plausible data. The generated instances become negative training examples for the discriminator.</li> </ul>
   <ul><li>The discriminator learns to distinguish the generator's fake data from real data. The discriminator penalizes the generator for producing implausible results </li>
  </ul>
  

 </ul></ul>
 
 <ul><li> <b>When training begins, the generator produces fake data, and the discriminator
quickly learns to tell that it's fake:</b><li> </ul>
<ul><ul><img src=https://user-images.githubusercontent.com/75990647/192567303-3786130c-c169-49b8-af6a-77bb0e20138e.png
 width="800px"></ul></ul>
 <ul><li><b>As training progresses, the generator gets closer to producing output that can fool
the discriminator:</b><li></ul>
 <ul><ul><img src=https://user-images.githubusercontent.com/75990647/192566125-4b9e9672-3632-4e4e-947e-eb68c0d1585e.png
 width="800px"></ul></ul>
  <ul><li><b>Finally, if generator training goes well, the discriminator gets worse at telling the
di erence between real and fake. It starts to classify fake data as real, and its
accuracy decreases.</b><li></ul>
<ul><ul><img src=https://user-images.githubusercontent.com/75990647/192568846-79cd1b08-b6e2-4178-8a02-8cc3766c4a73.png width="800px"></ul></ul>
<ul><li><b>Here's a picture of the whole system:</b><li></ul>
 <ul><ul><img src=https://user-images.githubusercontent.com/75990647/192569381-fefa52be-9a8b-4c91-b4eb-37c8a8fca300.png width="800px"></ul></ul>
 <ul><li><b>Both the generator and the discriminator are neural networks. The generator
output is connected directly to the discriminator input. Through backpropagation,
the discriminator's classiﬁcation provides a signal that the generator uses to
update its weights.</b><li></ul>
 
  <ul><li><strong> ----------------------- THE DISCRIMINATOR -----------------------</strong></li><ul>
 <ul>
  <li>The discriminator in a GAN is simply a classiﬁer. It tries to distinguish real
data from the data created by the generator. It could use any network architecture
appropriate to the type of data it's classifying.</li>

<ul><ul><img src=https://user-images.githubusercontent.com/75990647/192743996-a5e9e788-4ae7-4752-b995-6e18faf85077.png width="800px"></ul></ul>

<li><strong> DISCRIMINATOR TRAINING DATA : </strong></li>
  The discriminator's training data comes from two sources:
  <li>Real data instances, such as real pictures of people. The discriminator uses
these instances as positive examples during training.</li>
  <li>Fake data instances created by the generator. The discriminator uses these
instances as negative examples during training.</li>
  
  In Figure 1, the two "Sample" boxes represent these two data sources
feeding into the discriminator. During discriminator training, the generator does not
train. Its weights remain constant while it produces examples for the discriminator
to train on.
  
  </ul>
   <ul><li><strong> TRAINING THE DISCRIMINATOR </strong></li></ul>
   <ul>
   <li>The discriminator connects to two loss functions. During discriminator
training, the discriminator ignores the generator loss and just uses the
discriminator loss. We use the generator loss during generator training, as
described in the next section.

During discriminator training:
1. The discriminator classiﬁes both real data and fake data from the generator.
2. The discriminator loss penalizes the discriminator for misclassifying a real
instance as fake or a fake instance as real.
3. The discriminator updates its weights through backpropagation from the
discriminator loss through the discriminator network.</li>
   </ul>
   
 <ul><li><strong>
   ----------------------- THE GENERATOR -----------------------</strong></li><ul>
  <ul><li>The generator part of a GAN learns to create fake data by incorporating
feedback from the discriminator. It learns to make the discriminator classify its
output as real.

Generator training requires tighter integration between the generator and
the discriminator than discriminator training requires. The portion of the GAN that
trains the generator includes:
● random input
● generator network, which transforms the random input into a data instance
● discriminator network, which classiﬁes the generated data
● discriminator output
● generator loss, which penalizes the generator for failing to fool the
discriminator<li></ul>
  
  <ul><ul><img src=https://user-images.githubusercontent.com/75990647/192746211-344ca2e4-1bc7-4999-a3cf-44fa4a0eef3b.png width="800px"></ul></ul>
  
  <ul><li><strong> USING THE DISCRIMINATOR TO TRAIN THE GENERATOR </strong></li></ul>
  <ul><ul>To train a neural net, we alter the net's weights to reduce the error or loss of
its output. In our GAN, however, the generator is not directly connected to the loss
that we're trying to a ect. The generator feeds into the discriminator net, and the
discriminator produces the output we're trying to a ect. The generator loss
penalizes the generator for producing a sample that the discriminator network
classiﬁes as fake. Backpropagation adjusts each weight in the right direction by calculating the
weight's impact on the output — how the output would change if you changed the
weight. But the impact of a generator weight depends on the impact of the
discriminator weights it feeds into. So backpropagation starts at the output and
ﬂows back through the discriminator into the generator.

At the same time, we don't want the discriminator to change during
generator training. Trying to hit a moving target would make a hard problem even
harder for the generator.
So we train the generator with the following procedure:
1. Sample random noise.
2. Produce generator output from sampled random noise.
3. Get discriminator "Real" or "Fake" classiﬁcation for generator output.
4. Calculate loss from discriminator classiﬁcation.
5. Backpropagate through both the discriminator and generator to obtain
gradients.
6. Use gradients to change only the generator weights.</ul></ul>
  
 # WHITE-BOX-CARTOONIZATION:
  # ------------------------
  
 ### Examples : 
 
 <img src=https://user-images.githubusercontent.com/75990647/192364958-662bf141-95f8-4836-ad9e-dacbd4d97338.jpg
 width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192365094-9080ea94-d34d-469c-bd29-df20d82ee657.jpg
 width="400px"/>
 
<img src=https://user-images.githubusercontent.com/75990647/192308302-3f836f7b-4d7b-4419-b5c0-8de27f1e4dc0.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192308594-ffe78b53-8b29-4003-bcf6-b6dc4fb71512.jpg width="400px"/>


<img src=https://user-images.githubusercontent.com/75990647/192309412-c6726bd0-5991-453e-8129-d6e967bbf968.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192309485-17a023b5-cdbd-496a-b0c8-6c824c89fd05.jpg width="400px"/>

<img src=https://user-images.githubusercontent.com/75990647/192309598-cf86dc2d-631c-43c3-b666-16f00b246026.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192309724-9ab3f00c-a3c0-4eee-8c20-1241dcd68a34.jpg width="400px"/>
 
 
<img src=https://user-images.githubusercontent.com/75990647/192365850-d9cacdc2-560f-416b-93f5-de30485cb6e3.jpg
 width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192365908-663596be-90d3-4e29-9ce5-7a060dd31333.jpg
 width="400px"/>

<img src=https://user-images.githubusercontent.com/75990647/192565009-b43cf5bf-01c5-47f1-8a8b-35730de3a85e.jpg
  width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192565068-1db03857-29b5-41a3-9ba8-bc14065cf437.jpg
  width="400px"/>
 
<img src=https://user-images.githubusercontent.com/75990647/192309810-b78c79a9-8eb7-4669-beda-dccac873f460.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192309909-b46b17d8-743f-4ab2-8ef2-365641c21695.jpg width="400px"/>
 
<img src=https://user-images.githubusercontent.com/75990647/192361542-10893efc-cbf6-42db-92ee-fd350b864ced.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192361692-6d54bfdc-90c7-4593-827b-001ddae13d8d.jpg width="400px"/>
 
<img src=https://user-images.githubusercontent.com/75990647/192362349-75488d2b-7463-4fa0-a74f-37ce59ec87bc.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192362428-aa694692-ef8f-4b31-9334-f0743d8477b9.jpg width="400px"/>
 
<img src=https://user-images.githubusercontent.com/75990647/192363134-b4ee4356-5e3a-4fd1-871f-3bddd364df03.jpg
width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192363186-6a484e04-ecff-4b34-a206-66ce98086052.jpg width="400px"/>
 
<img src=https://user-images.githubusercontent.com/75990647/192364296-b06f61ca-723b-4130-ad33-964e235969e2.jpg width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192364356-e3e695a7-3adb-48d7-bb1e-a14e3e0b58e5.jpg
 width="400px"/>
 
 <img src=https://user-images.githubusercontent.com/75990647/192366642-482c6960-c682-4c03-84b0-71fbade5b016.jpeg
 width="400px"/>
<img src=https://user-images.githubusercontent.com/75990647/192366682-c45479c3-d0e0-4f31-876e-4d7b77fcf799.jpg
 width="400px"/>

 
