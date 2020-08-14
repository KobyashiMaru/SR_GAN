# SRGAN
Using GAN to solve super resolution problem

The work is for my man Billy Herrington, forever aniki.

![Billy_Herrigtin](https://i.imgur.com/bdyl1pP.jpeg)

SRGAN, aka super resolution GAN. Its main goal is to make a low resolution photo to be high resolution. Thus, it is a image restoration problem.


## Algorithm
Trained by Flickr 30k dataset. Which is a dataset made by Flickr of course, the dataset contain roughly 30,000 high resolution pictures. Thus, the full algorithm being, we make a function to let those pictures look like crap. Then, we got 30k high resolutioon images, and 30k low resolution images. Then we use those 60k images as training data, and testing data, feed into SRGAN. After we think we had trained enough, we can start let our model it into production.









