---
layout: post
title:  "Latch and Gear Iterations"
date:   2024-03-11 14:00:00 -0400
categories: jekyll update
---

Below is an assembly of the first iteration of the latch and gear design.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/latch_v1.jpg" alt="drawing" width="300"/><br>
<em>Latch and Gear V1</em>
</p>

The latch and gear teeth are designed aggresively so that the latch hooks on when in engaged position. However, the issue with this design is that the latch does not disengage naturally, since the spring-tensioning in the gear pushes back against the latch with greater force than the solenoid retraction spring. We needed to pull on the cable to allow the latch to disengage.

<p style="text-align: center;">
<video width="600" height="350" controls>
  <source src="{{site.baseurl}}/assets/media/latch_v1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Latch and Gear V1</em>
</p>

<br>

The second iteration of the latch and gear attempts to solve this issue by introducing a convex curve to the backs of the gear teeth. However, the issue still persists in the latch where it does not spring back when the solenoid is not triggered.

<p style="text-align: center;">
<video width="350" height="600" controls>
  <source src="{{site.baseurl}}/assets/media/latch_v2.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Latch V2</em>
</p>

This was fixed by filing down the tip of the latch, but this brings up another issue of not being able to keep the gear locked in the engaged position.

<p style="text-align: center;">
<video width="350" height="600" controls>
  <source src="{{site.baseurl}}/assets/media/latch_v2_filed.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Latch and Gear V2 (Filed)</em>
</p>
<br>

The latch-gear system is redesigned in the third iteration so that the latch is longer and the solenoid line of motion is angled instead of straight up. A careful balance of having enough aggression on the latch and gear teeth and having the latch be always retractable finally leads to a working design iteration.

<p style="text-align: center;">
<video width="350" height="600" controls>
  <source src="{{site.baseurl}}/assets/media/latch_v3.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Latch and Gear V3</em>
</p>
<br>

Below is the a front view of final CAD of the latch, linkages, and gear configuration.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/final_cad_front_view.png" alt="drawing" width="400"/><br>
<em>Final CAD Front View</em>
</p>
