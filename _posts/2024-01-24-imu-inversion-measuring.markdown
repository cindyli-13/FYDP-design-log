---
layout: post
title:  "IMU Inversion Measuring"
date:   2024-01-24 14:30:00 -0400
categories: jekyll update
---

## IMU Coordinate System

To measure ankle inversion speed with the double IMU setup, we need to figure out a way of referencing IMU measurements in the same frame of reference. The IMUs are mounted on the foot with approximately the following configuration:
- IMU A with reference frame {a} mounted on the lower leg
- IMU B with reference frame {b} mounted on the foot

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/imu_frames.png" alt="drawing" width="300"/><br>
<em>IMU Sensor Frames</em>
</p><br>

We need to obtain the rotation matrix $$R_b^a$$ which maps from sensor frame {b} to sensor frame {a}. To do this, obtain the normalized acceleration vectors measured by the IMUs at resting position (call them $$\hat g_a$$ and $$\hat g_b$$). These are the measured unit gravity vectors in frames {a} and {b} respectively. Then:
- Let $$v=\hat g_b\times \hat g_a$$
- Let $$c=\hat g_b\cdot \hat g_a$$

Then the rotation matrix can be computed as:

$$R_b^a=I+[v]_x+[v]_x^2 \frac{1}{1+c}$$

where

$$[v]_x:=\begin{bmatrix}0&-v_3&v_2\\v_3&0&-v_1\\-v_2&v_1&0\end{bmatrix}$$

is the skew-symmetric cross-product matrix of $$v$$ ([source](https://math.stackexchange.com/questions/180418/calculate-rotation-matrix-to-align-vector-a-to-vector-b-in-3d/)).

<br>

With the above mounting scheme, if we assume that the positive inversion direction is rotation about the $$x_a$$ axis (referenced in sensor frame {a}), then we can measure inversion velocity as:
    
$$\omega_{inversion}=(R_b^a\omega_b-\omega_a)_1$$

where $$\omega_a$$ and $$\omega_b$$ are gyroscope measurements from IMUs A and B, respectively. Note that $$(x)_1$$ here means the first element of vector $$x$$.

<br>

## Testing
The following video shows the test setup of the IMU inversion measuring scheme. The live plotter shows the measured inversion velocity in degrees per second of the model test foot.

<p style="text-align: center;">
<video width="800" height="400" controls>
  <source src="{{site.baseurl}}/assets/media/imu_inversion_measuring_test.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</p>
