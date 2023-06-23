# Integrating Real-Time Pothole and Lane Detection in Raspberry Pi 4
Members: Taesun Yeom (team leader) , Hyunjun Shin. (Advised by Prof. Seokwon Lee)

For course of Capstone Design (1) (2023-1), mechanical engineering in Chung-Ang University.

Our objective is to integrate methods of real-time lane detection (directional guidance for servo motor) and pothole detection (obstacle detection) using Arduino Mega and Raspberry Pi 4

# Introduction

From the perspective of objective detection, it is hard to perceive obstacle in low-brightness condition (e.g.,night, tunnel, cloudy weather).
We adopt simple data augmentation technique for dealing the problems, while provide real-time processing through Raspberry Pi 4.
However, since Raspberry Pi's computational speed is extremely low, We applicate ncnn library by tencent inc. , which provides faster compute speed on low-cost devices.

# Method

We adopt YoloX-nano, which provides real-time detection and 'nano-sized' network(extremely small size), fitted to our objectives. 

1. Since our objective is to detect 'potholes', custom training is required. Prepare own pothole dataset with corresponding bounding box annotation. Note that vanilla-YoloX is trained for 80 classes.

2. 'https://Roboflow.com' provides public dataset of potholes. Be sure to download as 'VOC' format, which annotations(.xml) fits to YoloX bounding box structure. If you already have data and corresponding bounding box, you don't have to download.

3. Training your own dataset for YoloX-nano. You can check some information in [YoloX](https://github.com/Megvii-BaseDetection/YOLOX). Change checkpoint file to 'AAA.onnx' for RPI4 adaptation. Then change 'AAA.param','AAA.bin' in RPI4 using 'onnx2ncnn' file. 

4. Prepare Raspberry Pi 4 (64bit os), and turn the camera on. You can test camera by
```
libcamera-hello
```

4. To enchance FPS for lane and pothole detection, we adopt C++ structure rather than Python. By using [ncnn](https://github.com/Tencent/ncnn), we observed that 8~9 FPS for total task. For C++, please download 'CodeBlocks' and open 'lane.cbp'(the project file. This file contains other dependent files.. e.g., lane, pothole detection, picamera)

5. Final step. Run the code and watch how it drives.

Codes will be released shortly!

# Result




# Acknowledgement

Thanks for helpful advise to our supervisor (Prof. Seokwon Lee) ! 
