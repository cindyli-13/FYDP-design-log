---
layout: post
title:  "Software Architecture"
date:   2023-11-20 00:00:00 -0400
categories: jekyll update
---

Below is a high block diagram of the ESP32-S3 microcontroller system and interfacing components.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/software_block_diagram_high_level.png" alt="drawing" width="800"/>
<em>ESP32 System Interfaces</em>
</p><br>

To take advantage of the dual-core setup of the ESP32-S3, core 1 will hold the state machine logic and perform sensor/actuactor interfacing, while core 2 will handle all networking tasks. A communication channel between the two cores will be set up using shared memory. Below is the software block diagram showing the responsibilities of each core.

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/software_block_diagram_detailed.png" alt="drawing" width="800"/>
<em>Software Architecture Block Diagram</em>
</p><br>

<p style="text-align: center;">
<img src="{{site.baseurl}}/assets/images/activity_state_machine_block_diagram.png" alt="drawing" width="800"/>
<em>Activity State Machine Block Diagram</em>
</p>
