---
layout: post
title:  "Software State Machine Implementation"
date:   2024-02-24 14:00:00 -0400
categories: jekyll update
---

The activity state machine is the main logic block that runs on the ESP32 microcontroller. It handles all the state logic for Calibrating, Idle, Active, and Actuated states. The state machine runs at a 1kHz loop to ensure a fast response time to IMU readings.

### Calibrating
This is the first state upon starting up the system. During calibration, the foot should be kept still for 3 seconds. The system collects sensor (accelerometer) data for 3 seconds which is used to determine the correct IMU orientations for inversion measurement. After calibration is complete, the system transitions to the Idle state.

### Idle
The idle state is meant for power saving. A transition to the Active state happens when the system detects foot motion.

### Active
In the Active state, the system is ready to trigger the actuation mechanism whenever it detects an inversion event (eg. when the measured inversion speed exceeds 400 degrees per second). A transition to the actuated state happens when an inversion event occurs and the system triggers the solenoid. A transition to the Idle state happens if the system does not detect foot motion within 60 seconds.

### Actuated
The system stays in the Actuated state for 2.5 seconds then untriggers the solenoid and returns to the Active state.

## Initial Bring-up
The activity state machine was initially brought up with a Dev board and solenoid and IMUs setup. Upon detecting a high enough inversion speed through the double IMU setup, the solenoid is triggered. The onboard RGB LED indicates the system state (green = Active, red = Actuated).

<p style="text-align: center;">
<video width="700" height="400" controls>
  <source src="{{site.baseurl}}/assets/media/solenoid_trigger_test.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<em>Working State Machine Test</em>
</p>

## Impact Detection
The original goal was to also trigger upon detecting a high impact force to the foot (eg. landing after a jump). However, during our testing, we noticed that light impacts such as a light hop or stomp oversaturated the IMU accelerometer readings (the ICM-20948 accelerometer has a maximum full-scale range of 16 G's, while jumping and landing can produce up to 60 G's). Thus, we will not be incorporating impact detection in our system and will only rely on gyroscope inversion speed readings for detecting ankle inversions. Impact detection may be a possible future extension with higher specced IMUs.
