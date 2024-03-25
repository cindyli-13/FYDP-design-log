---
layout: post
title:  "Final Assembly and Testing"
date:   2024-03-24 14:30:00 -0400
categories: jekyll update
---

We assembled our final prototype with machined aluminum parts, rev 2 PCB, and 3D-printed resin housing cover.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/final_assembly.jpg" alt="drawing" width="300"/><br>
<em>Final Brace Assembly</em>
</p>

<br>

Below are videos of our testing trials verifying that the brace is working as intended. Slow ankle movements do not trigger the actuation mechanism. When a high enough ankle inversion speed is detected, the brace triggers and stiffens the cable to prevent further inversion. Telemetry streaming over Wi-Fi is implemented with the data (eg. actuation state, ankle inversion speed plot, battery health, configuration parameters) displayed live through a UI on the host machine. The UI also allows us to easily recalibrate the brace or change the configuration parameters.

<br>

<p style="text-align: center;">
<video width="800" controls>
  <source src="{{site.baseurl}}/assets/media/demo_active_wifigui.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Final Brace Demo with Live Telemetry UI</em>
</p>

<br>

<p style="text-align: center;">
<video width="300" controls>
  <source src="{{site.baseurl}}/assets/media/demo_onankle.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Final Brace Demo on Ankle</em>
</p>
