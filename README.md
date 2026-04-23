# PACK-E
MSP432 Robot Chassis with ESP32 Camera Detection

## Project Description:
Using the ESP32CAM to detect and classify packages and then move to package and grab it.
Custom-trained object detection model using:
- FOMO MobileNetV2 0.1 as neural network architecture
- TFLite Micro as inference engine/library
- Edge Impulse as platform for training model on dataset
For computer vision part:
- Finds centroid of each objects, outputs object x, y coords
- Caclulates error between object centroid and camera center frame,
- Maps error to rotation speed until robot reaches center


96 x 96 resolution yolo();, rgb565 //to save ram
//change metadata if u want to have higher resolution
//change to vga(); 640 x 480 with jpeg encoding, with PSRAM u can do it

## Components used:
- UART
- Servo
- Motor
- Freenove ESP32S3 Wroom 1 with OV3660
- Ultrasonic - For finding object location

## Original conceptualization

## Obstacles faced
- Kept giving me brownout detector error - fixed it by removing line camera.brownout.disable();
- Example code from eloquent library did not have PSRAM enabled, modified code and tools to enable PSRAM
- <img width="595" height="832" alt="image" src="https://github.com/user-attachments/assets/d8d688a6-5f70-4eb5-9e6f-38de9cb9a7bf" />
- use 16MB Flash, with OPI PSRAM and 16MB 3APP partition
- Ran into multiple and heap problems running my model, EON compiler was giving many issues with the Eloquent Arduino library
- TFLite Micro was compatible, although TFLite is less optimized for embedded ML
## Testing and verification

## Pictures or videos

## Possible improvements with more time:
- Stereo Camera Pair with distance estimation
- Laptop Command via ROS2
