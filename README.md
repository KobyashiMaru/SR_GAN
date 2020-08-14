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

So Let's talk about the generators first, we use resnet-34 U-Net to do the job.



