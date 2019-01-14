I am an amateur astronomy enthusiast who enjoys celestial photography using a method of stacking a large amount of short exposure with CMOS imager.

Here, when stretching dark and sparse objects such as diffuse nebulas, I had a problem with cold pixels. Also, compared to CCD, CMOS imager is subject to variation in sensitivity of each pixel.

I already knew that there is a technique called dithering to solve these problems. However, I do not care even auto guiding. My shooting environment is unstable and soft balcony so it's hard to set up and operate. So, I thought about how to solve this problem more easily if possible.

In such circumstances, I saw this blog article. https://apranat.exblog.jp/28129764/　(Please translate it using google translate etc. because it is Japanese) In this wonderful article he investigated that cool pixels can not be eliminated even with dark frames or regular flat frames. The reason is being analyzed on this page.

The cold pixel is not a pixel that is not working at all, it is a pixel with considerably low sensitivity. And, its sensitivity should decrease nonlinearly with decreasing light quantity. Then, he figured out a method to recognize and remove cool pixels, but I thought cool pixels as "effective pixels with extremely low sensitivity but effective pixels" and by improving the accuracy of the flat frame, I attempted to eliminate the dispersion of sensitivity. Because it's easier to post-process and the processing method can basically be handled the same as the flat frame. And it seems to be compatible with live stacking.

