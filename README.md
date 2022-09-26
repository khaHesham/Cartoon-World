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


