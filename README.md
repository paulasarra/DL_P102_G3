# DL_P102_G3
Emotion Based Face Generation GAN

The objective is to generate new images that look like real faces. For that, we need a deep network in which we will input random noise and that is able to generate images from it. But how can we teach this network, which we call the generator,  to learn a meaningful mapping (so to go from something like noise to actual faces that seem real)? Here is when another network appears to help the generator, which is the discriminator network. How will we use it?
Well, we will input images into this network, but these images will come alternatively from two sources: one source will be the fake images coming from the generator and another source will be some images coming from a real dataset, so real faces. And the task of this discriminator is just to output if the image he receives is real or fake, so it is just like a binary classifier.
This combination is called an adversarial network because these two networks have opposite goals: the generator wants to fool the discriminator with his fake images, whereas the discriminator wants to realise when an image is fake.
In the end we have to think about the fact that we are in an unsupervised setting, we have  a lot of images but we have no labels, and having this discriminator network gives us a way to generate these labels. So that during the training the discriminator can tell the generator okay, now you are creating something close to a real face because it is getting more difficult for me to distinguish . And from that the generator will learn. 
So in practice, how will it be this process of learning? The discriminator will back propagate something, and this something will be a loss. 
And it is important to know that we have to be careful because if the discriminator gets too good from the beginning of the training, so it performs and distinguishes perfectly too early, then its loss will be zero and thus there will be nothing to backpropagate, no gradient, and as a consequence the generator would have no way to learn and improve. 
