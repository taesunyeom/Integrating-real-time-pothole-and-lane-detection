# Real-Time Pothole Detection in Raspberry Pi 4

For course of Capstone Design (1), mechanical engineering in Chung-Ang University.

Intergrating lane detection (directional guidance) & pothole detection (obstacle detection) using Arduino Mega & Raspberry Pi 4

# Introduction

From the perspective of objective detection, it is hard to perceive obstacle in low-brightness condition (e.g.,night, tunnel, cloudy weather).
We adopt simple data augmentation technique for dealing the problems, while provide real-time detection using Raspberry Pi 4.
However, since Raspberry Pi's computational speed is extremely low, We applicate ncnn library by tencent inc. , which provides faster compute speed on low-cost devices.

# Method

We adopt YoloX, which provides real-time detection and 'nano-sized' network(extremely small size), fitted to out objectives. 

1. Since our objective is to detect 'pothole', custom training is required. Prepare own pothole dataset with corresponding bounding box annotation. Note that vanilla-YoloX is trained for 80 classes.

2. 'https://Roboflow.com' provides public dataset of potholes. Be sure to download as 'VOC' format, which annotations(.xml) fits to YoloX bounding box structure. If you already have data and corresponding bounding box, you don't have to download.

3. To

# Result




# Acknowledgement
