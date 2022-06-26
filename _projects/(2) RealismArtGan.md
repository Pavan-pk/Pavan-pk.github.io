---
name: RealismArt GAN
tools: [Pytorch]
image: /images/sample.png
description: Translating real images to Realism art style images.
---

# RealismArt GAN
Translating real images to Realism art style images. As this art style dates back to the 17th century and there is no image-to-image pair data available to train traditional style transfer networks, We have to go with unpaired image-to-image translation techniques. In this project, I'm exploring one such concept which uses 2 GAN networks with cycle consistent objective function between the networks.
With this network, it is possible to generate realism-styled images of the current world and real-world-like photos from realism art-styled paintings.<br>

### Datasets<br>
1. For Realism art images, I used the realism image folder from the dataset https://github.com/cs-chan/ArtGAN/tree/master/WikiArt/Dataset
(All images are copyrighted and can only be used for academic research purposes.)
Example: ![preview](/images/example_art.png)
2. For picking real images, I have evaluated the art images and found domains like landscape, indoor, and portrait.<br>
I have picked landscape images from the Flicker dataset for cartoonGAN, the Indoor dataset from Recognizing Indoor Scenes paper, and Portraits from FFHQ dataset.

### Training<br>
This network has 2 GANs with 3 objective functions to minimize (loss functions):
1. Adversarial loss, loss of a GAN to discriminate generated vs real image. (There are 2 discriminators one to discriminate X samples and another Y and use generated vs real image to discriminate). 
2. Cycle consistency loss is a loss function between {(G(F(Y)), X}, which is the loss calculated between generated X(after a cycle) vs actual X.
3. Identity loss is a loss function of {F(Y), Y}. This function helps the network to identify if an image belongs to the same domain.

### Evaluation<br>
I used a new evaluation technique as defined in the paper A Novel Measure to Evaluate Generative Adversarial Networks Based on Direct Analysis of
Generated Images (https://arxiv.org/pdf/2002.12345.pdf) which is more suited for this task as it defines a likeness score as a combination of Creativity, Inheritance, and Diversity.<br>
The baseline likeness score on the dataset was: 0.26<br>
After training the resultant likeness score was: 0.94<br>

### Samples
![preview](/images/RealismArt.png)


<p class="text-center">
{% include elements/button.html link="https://github.com/Pavan-pk/RealismArtGan" text="Project repository" %}
</p>