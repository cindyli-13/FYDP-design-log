---
layout: post
title:  "AB Testing"
date:   2024-03-18 14:30:00 -0400
categories: jekyll update
---

## Criteria
Each item below is tested on the foot model with and without the protection engaged.

1. Time stayed above 400 deg/s inversion speed
2. Stopping position of ankle

## Procedure

1. Pull the string attached to the foot brace with a gentle jerk motion with the protection engaged.
2. Record the IMU’s inversion speed reading as well as the video of inversion sequence.
3. Take a photo of the ankle’s final position.
4. Repeat without the protection.

Note: due to limitation in 3D printed mechanism causing slipping in gear and latch, inversion motion is tested with manual pulling of string instead of dropping weight at fixed height. The test is to be repeated when machined parts are assembled.

## Results

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/AB_test.png" alt="drawing" width="800"/><br>
<em>AB Test Results</em>
</p>

Looking at the inversion speed plots on the left side of the figure above, a clear difference in the width of the inversion speed pulse can be seen. The inversion speed without protection engaged stays above 400 deg/s for more than ~40 ms. This results in the foot model hitting the maximum range of motion of about 48 degrees in less than 100 ms. 

In contrast, inversion speed with brace stays above 400 deg/s for a single IMU sample only, and sharply dropping afterwards. The effectiveness of brace can be seen in the inversion angle plot on the bottom right side of the figure as well. The protection mechanism engages in less than 50 ms of ankle inversion starting and stops the ankle at about 22.5 degrees.

<br>

Below pictures and videos are from the AB testing above.

With protection engaged:

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/ab_test_with_brace.jpeg" alt="drawing" width="400"/><br>
<em>Ankle Inverted Position With Brace Protection</em>
</p>
<br>

<p style="text-align: center;">
<video width="400" controls>
  <source src="{{site.baseurl}}/assets/media/ab_test_with_brace.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Test With Brace Protection</em>
</p>
<br>

Without protection engaged:

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/ab_test_without_brace.jpeg" alt="drawing" width="400"/><br>
<em>Ankle Inverted Position Without Brace Protection</em>
</p>
<br>

<p style="text-align: center;">
<video width="400" controls>
  <source src="{{site.baseurl}}/assets/media/ab_test_without_brace.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Test Without Brace Protection</em>
</p>
<br>
