---
layout: post
title:  "Integrated Testing"
date:   2024-03-09 14:00:00 -0400
categories: jekyll update
---

Today we performed fully integrated tests on the brace prototype, the main purpose being to verify our design constraints:
- 40ms response time
- Brace triggers and latches at >400dps inversion speed, prevents further inversion of ankle

Below is a photo of our test setup with the 3D-printed brace prototype mounted on the test foot model mounted on a wooden test platform.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/integrated_test_setup.jpg" alt="drawing" width="500"/><br>
<em>Test Setup</em>
</p><br>

## Test 1 - Response Time

#### Test Procedure
- Mount model foot with brace on test platform, string attached to sole of foot
- Run youtube 120fps stopwatch on laptop, place visibly by test platform
- Set up phone to film test setup from an appropriate angle (film in slo-mo)
- Manually pull on string to trigger an inversion event
- Review slo-mo video, record time from when yellow trigger LED turns on to when latch engages with gear
- Run 3 trials

<br>

#### Test Video
<p style="text-align: center;">
<video width="700" height="400" controls>
  <source src="{{site.baseurl}}/assets/media/response_time_test.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</p>
<br>

#### Test Results

| Trial | Response time (ms) |
| --- | --- |
| 1 | 25 |
| 2 | 26 |
| 3 | 16 |

**Pass criterion:** response time of all 3 trials are under 40ms - TEST PASSES!

<br>

## Test 2 - Weighted Pulley Test

#### Test Procedure
- Mount model foot with brace on test platform, string attached to sole of foot and pulleyed over hook
- Set up phone to film test setup from an appropriate angle
- Connect dev board to laptop, run Python script to plot measured inversion speeds in real-time
- Attach weight to end of string, let go, expect brace to prevent full inversion
- Re-drop the weight after a few seconds to show that brace is able to reset automatically and is capable of re-triggering

<br>

#### Test Video
<p style="text-align: center;">
<video width="700" height="400" controls>
  <source src="{{site.baseurl}}/assets/media/weighted_pulley_test.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</p>
<br>

**Pass criterion:** brace triggers and prevents full inversion every time measured inversion speed surpasses 400dps - TEST PASSES!

<br>

## Test 3 - Correctness of Inversion Measuring

#### Test Procedure:
- Set up phone to film test setup from an appropriate angle
- Connect dev board to laptop, run Python script to plot measured inversion speeds in real-time
- Hold brace, move around foot part, together with lower leg, inversion motion, dorsiflexion motion

<br>

#### Test Video
<p style="text-align: center;">
<video width="700" height="400" controls>
  <source src="{{site.baseurl}}/assets/media/inversion_measuring_test.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</p>
<br>

**Pass criterion:** only inversion motion is measured as seen by the live plotter, dorsiflexion and other movements do not register as large spikes in measured inversion speed (qualitative test) - TEST PASSES!
