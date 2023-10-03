# Basic-Image-and-Video-Operations-using-OpenCV
Basic Image and Video Operations using OpenCV

# Basic Image Operations
In both parts, we are going to use OpenCV library for both image and video manipulations.
First, we upload the selected image and convert into a RGB photography since OpenCV uses BGR instead of RGB. This is our base image.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/9222912b-e4f1-4391-a305-9c5cb2ab9ccb)


### Crop Image from center
By using “shape” method, we got the shape of images. This shape includes height, width, and channel information. To find out the center of the height and width, we are dividing them 2. 
After that, we define a number for how much crop we apply. I defined as 100. This is the cropping of the base image from center.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/a07b021c-3139-465e-9e36-3a0dc3a8fc6b)


### Extract Red Channel
By using opencv split method, we can extract all the channel of images like b,g,r. This is the Red Channel of Image

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/adb42411-9e81-40b2-b096-63d5e0916740)


### Gray Scale Image
By using OpenCV “cvtColor “method, we can convert image’s colors into a different color space such as BGR to RGB, RGB to HSV, GRAY to RGB etc. This is the Gray Scale of Image.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/c775efb4-9586-41c0-b729-430f2ea0ba8c)


## Sobel Filters
The Sobel Operator is a discrete differentiation operator. It computes an approximation of the gradient of an image intensity function. 
So, basically Sobel filters used for edge detection. To apply the sobel filter, we are using 3 by 3 kernel by predefined. These are called Gx and Gy. As seen on the images, Gy filter transpose of the Gx filter.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/e101acd4-f59c-41d3-919f-ae47e5a3b07e)

For define the sobel filter on python, we are using np.array function. After define the filter, we are applying filter to the gray scale image by using cv.filter2D function. After that, we are converting this image into the uint8.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/b3d45297-dd00-4ad6-9532-2f4914ada81c)


### Gradient Magnitude
Gradient Magnitude is basically combining of Sobel X and Sobel Y filters. Gradient magnitude is simply the square-root of the squared gradients in both the x and y direction added together. To compute the gradient magnitude, we are using G=√Gx2+Gy2 formula.
This is how look like gradient magnitude.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/31a98828-08b5-4514-9764-6cd86fadcfac)


### Gradient Orientation
Gradient orientation is the arctangent of the gradients in both the x and y direction. To compute the gradient orientation, we are using 𝜃=𝑎𝑡𝑎𝑛_2(𝐺𝑦,𝐺𝑥)∗(180/𝜋)%(180) formula. This is how look like gradient orientation.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/e03d8d85-52d8-4775-aff7-0871d2fa7878)


## Laplacian of Gaussian
Another method of edge detection is Laplacian of Gaussian. To apply the LoG operation, first, we apply the gaussian blur on the image and convert the image into the gray scale. Final, 
we apply Laplacian formula on the image. To understand the difference of LoG, we used different sigma value on image.

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/ce5c9435-762c-4d94-acfe-ead7a9e77abe)


# Basic Video Operations
This the same with the first part however we have small changes on the code. To get the video from the computer, we are using videocapture method. After we are creating a while loop since we need to get frame constantly. All the process are happening inside of the loop.

### Sobel filters on video frames

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/58ac9736-27c7-4759-93a6-7fe732bdd5ce)

### Video Frame and Gradient Magnitude

![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/7caff5d9-923a-47ca-904b-2552364758eb)

### Combined Frame and Gradient Magnitude
In this part, we should be care about video size. Since we combined to frame, the width size will be double size. So, while we are recording a video, we make sure about width and height size are correct, or it will be giving an error. Also, we need to convert the gradient magnitude channel to 3 like GRAY to BGR, or it will give concatenation error.


![image](https://github.com/onlinEngineer/Basic-Image-and-Video-Operations-using-OpenCV/assets/70773825/a5b4253f-7e32-47e7-b08a-c167345ff1bc)
