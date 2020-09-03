# SRGAN
Using GAN to solve super resolution problem

The work is for my man Billy Herrington, forever aniki.

![Billy_Herrigtin](https://i.imgur.com/bdyl1pP.jpeg)

SRGAN, aka super resolution GAN. Its main goal is to make a low resolution photo to be high resolution. Thus, it is a image restoration problem.


## Show case

### Before SRGAN
![Ricardo_Before](https://imgur.com/HUiPzJA.png)

### After SRGAN Twice

![Ricardo_After](https://imgur.com/Hv3CIQT.png)

## Algorithm
Trained by Flickr 30k dataset. Which is a dataset made by Flickr of course, the dataset contain roughly 30,000 high resolution pictures. Thus, the full algorithm being, we make a function to let those pictures look like crap. Then, we got 30k high resolutioon images, and 30k low resolution images. Then we use those 60k images as training data, and testing data, feed into SRGAN. After we think we had trained enough, we can start let our model it into production.

### 1. Crappified Function
First of all, we need shitty images to train SRGAN, so we need to make our high resolution dataset look like shit. As a result, we make a function that not only can make images like crap, but also make some blank rectangles, we hope that we can train our model filling out some blank spots. The crappified function is coded by OpenCV.

### 2. SRGAN
We know that GAN contain 2 neural networks, which is generator and discriminator. In SRGAN, the goal of the generator is to generate HD picture out of a crappy picture. And the discriminator's job is to identify the picture is weather a high resolution images or not, thus the discriminator is basically a binary classifier. 

#### Generator
So Let's talk about the generators first, we use Resnet-34 U-Net to do the job. Like we mentioned before, the generator's job is to generate HD images. We use the advantages of U-Net that can output whole image and understand which pixel is which. Thus, we use MSE as loss function to make HD images. 


#### Discriminator
If you think why do we need another neural network model to generate HD images when generator's job is generating HD images itself? That's when you're deadly wrong lol. Yes, generator's job is generating HD images itself, but one neural network is not good enough. We need another model to tell us how the model is performed, that is to say, discriminator is the loss function itself. And like we said, discriminator is a binary classifier with BCE logit loss as loss function, its job is to tell a picture is a HD image or not. 

Thus, as everyone knows, we use these models to train each other. If the generator's perfofrmance is good enough, we shall go ahead and train the discriminator. Vice versa, if discriminator's performance is good enough, we train the generator. Since the computing resource is limited, my shitty laptop cannot handle the power of GAN, I have to train the generator and dicriminator a little bit, separately. This way, both model can understand what their jobs are, then we set up the SRGAN. This can make GAN converge quickly and use less computation resources. 


## Put GAN into Production


