<p align="right">Language: <a href="https://satakagi.github.io/sameConditionFlatFrame/">English</a>, <a href="https://translate.google.com/translate?sl=en&tl=ja&u=https%3A%2F%2Fsatakagi.github.io%2FsameConditionFlatFrame%2F">Japanese (Google Translation)</a></p>

## Introduction

I am an amateur astronomy enthusiast who enjoys celestial photography using a method of stacking a large amount of short exposure with CMOS imager.

Here, when stretching dark and sparse objects such as diffuse nebulas, I had a problem with cold pixels. Also, compared to CCD, CMOS imager is subject to variation in sensitivity of each pixel.

I already knew that there is a technique called dithering to solve these problems. However, I do not care even auto guiding. My shooting environment is unstable and soft balcony so it's hard to set up and operate. So, I thought about how to solve this problem more easily if possible.

In such circumstances, I saw [this blog article](https://apranat.exblog.jp/28129764/).　(Please [translate it using google translate](https://translate.google.com/translate?sl=auto&tl=en&u=https%3A%2F%2Fapranat.exblog.jp%2F28129764%2F) etc. because it is Japanese) In this excellent article he investigated that cold pixels can not be eliminated even with dark frames or regular flat frames. The reason is being analyzed on this page.

The cold pixel is not a pixel that is not working at all, it is a pixel with considerably low sensitivity. And, its sensitivity should decrease nonlinearly with decreasing light quantity. Then, he figured out [a method to recognize and remove cold pixels](https://apranat.exblog.jp/28135658/), on the other hand I thought cold pixels as "effective pixels with extremely low sensitivity" and by improving the accuracy of the flat frame, I attempted to eliminate the dispersion of sensitivity. Because it's easier to post-process and the processing method can basically be handled the same as the flat frame. And it seems to be compatible with live stacking.

## Same Condition Flat Frame
***Note: This method only has a little confirmation therfore is only a hypothesis. If you are interested, I am happy that you will validate the hypothesis and share it.***

### Hypothesis
There is a possibility that the flat frame has an effect of correcting variations in the sensitivity of pixels. However, if the sensitivity of a pixel varies nonlinearly, the flat frame captured in a bright environment does not work well. Therefore, it is preferable to use a flat frame captured using the same photographing condition under the same light amount as the object to be photographed.

### Practice
In order to verify this hypothesis, firstly I had to apply very little light to the CMOS imager. For this I decided to use a film that is used to shoot the sun. And controllable light.

This almost worked. I was able to acquire the condition not to be saturated with the exposure for 10 seconds, maximum gain (600) and temperature of -10 celsius with ASI1600MM-C. This shooting condition is often when I shoot the diffuse nebula with Hα filter. And I made a flat frame stacked from 300 frames using SharpCap's Flat Frame capture function. Then just set this "Same Condition Flat Frame" to SharpCap's Flat Frame and try live stacking!

#### Possible Issues
Because the light intensity is low, the flat frame will contain more noise. It may be possible to reduce it by stacking a lot, but how many stacks are appropriate? Also, since the brightness of the object is not uniform, the sensitivity that changes nonlinearly according to the brightness can not be completely eliminated by the flat frame

### Experimental result
#### Common conditions
* Exposure time/frame: 10 sec 
* 180 frames stacked (Total 30minutes)
* Imager: ASI1600MM-C (-10 degree celsius)
* Gain: 600 (Maximum)
* Binning:2
* Live Stacking / SharpCap (Pro3.2)
* Sigma-clipping

#### Reference image 1 (Without flat frame)
This is a live stacked image by SharpCap without using flat. Since guiding is not done, the cold pixels stretches and there are diagonally striped AKA "Walking Noise". The image is quite stretched so that noise emerges.

![Without flat frame](/img/nonFlat.png) 


#### Reference image 2 (A normal flat frame was applied)
This is a live stacked image using a normal flat frame made in a bright environment with short exposure and low gain. All other conditions are the same as above. Although it is a little weak, stripes appear in the horizontal direction. The direction of the stripe is different because the direction of the tracking deviation changed.

![A normal flat frame was applied](/img/normalFlat.png) 


#### The Result: "Same Condition Flat Frame" is applied
This is a live stacked image applied the "Same Condition Flat Frame". All other conditions are the same as above.
How about that. I think that the striped pattern has become almost invisible. Just to be sure, I tried shooting two photos on the same night.

![Same Condition Flat Frame-1](/img/sameFlat1.png)
![Same Condition Flat Frame-2](/img/sameFlat2.png)

