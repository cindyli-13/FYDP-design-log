---
layout: post
title:  "IMU Bring-Up"
date:   2023-11-16 10:00:00 -0400
categories: jekyll update
---

For sensing, we will primarily rely on IMU measurements to detect ankle inversion events. To detect the relative motion between the ankle and the foot, we will use 2 IMUs, one attached to the foot and one to the leg. The relative gyroscope readings between the 2 IMUs can be correlated to the angular velocity of the ankle joint.

We will be using 2 of SparkFun's breakout boards for the MPU-9250 IMU. This IMU is 9 DoF but we only care about the gyroscope and accelerometer readings. The sensor supports both I2C and SPI interfaces, but we will use SPI for the faster data transfer rates.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/imu_breakout_board.jpeg" alt="drawing" width="250"/><br>
<em>SparkFun IMU Breakout - MPU-9250</em>
</p>

Here is a video showing the proof of concept of the double IMU setup. The plotter shows the relative gyroscope measurements between the IMUs in degrees per second. Notice the spikes in measured angular velocity when the lower IMU rotates with respect to the upper IMU.

<p style="text-align: center;">
<video width="800" height="400" controls>
  <source src="{{site.baseurl}}/assets/media/double_imus_test.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</p>

### References
- [MPU-9250 Datasheet](https://invensense.tdk.com/wp-content/uploads/2015/02/PS-MPU-9250A-01-v1.1.pdf)
- [MPU-9250 Register Map](https://invensense.tdk.com/wp-content/uploads/2015/02/RM-MPU-9250A-00-v1.6.pdf)
