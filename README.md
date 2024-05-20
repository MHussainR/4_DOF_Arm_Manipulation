# Pick and Place Using a 4 DOF Manipulator

## Overview
This project demonstrates the implementation of a pick-and-place task using the Phantom X Pincher Arm and Intel Real Sense SR 305 Camera. The system utilizes object detection techniques, including color segmentation and k-means clustering, to identify blocks, followed by frame transformation to convert pixel positions to robot-friendly coordinates. Robot manipulation is achieved through forward and inverse kinematics solutions.

## Table of Contents
- [Introduction](#introduction)
- [Design Details](#design-details)
  - [Object Detection](#object-detection)
  - [Frame Transformation](#frame-transformation)
  - [Robot Manipulation](#robot-manipulation)
- [Results](#results)
  - [Object Detection](#object-detection-results)
  - [Frame Transformation](#frame-transformation-results)
  - [Robot Manipulation](#robot-manipulation-results)
- [Conclusion and Future Work](#conclusion-and-future-work)
- [References](#references)
- [Digital Material](#digital-material)

## Introduction
The objective of this project is to automate a pick-and-place task using a 4 DOF robotic arm, the Phantom X Pincher Arm, guided by the Intel Real Sense SR 305 Camera. The focus is on achieving efficient object detection and accurate robot manipulation using advanced algorithms and MATLAB commands.

## Design Details

### Object Detection
The system detects objects (colored blocks) using color segmentation and k-means clustering. The process involves:
1. **Taking the Image:** Capturing an image of the workspace using the Intel Real Sense SR 305 Camera.
2. **K-Means Clustering:** Converting the image to LAB color space and applying k-means clustering to identify different colored blocks.
3. **Identifying Colors:** Determining the color of each block using the RGB values at the center of the detected masks.

### Frame Transformation
The detected block positions, initially in pixel coordinates, are transformed into robot-friendly coordinates (meters) using the following steps:
- The x and y axes of the camera are inverted to match the robot's coordinate system.
- The center of the robot is established as a reference point.
- Pixel positions are converted to meters using a predetermined scale factor.

### Robot Manipulation
Robot movement is controlled using forward and inverse kinematics:
- **DH Parameters:** Define the robot's link parameters.
- **Inverse Kinematics:** Calculate joint angles to position the robot's end effector at the desired coordinates.
- **Finite State Machine (FSM):** Ensures smooth execution of the pick-and-place task by selecting the optimal joint movements.

## Results

### Object Detection Results
The object detection algorithm successfully identified all blocks with a 100% success rate in color identification.

### Frame Transformation Results
The frame transformation process exhibited an error rate of approximately 8% between the calculated and actual coordinates.

### Robot Manipulation Results
The robot achieved an 80% success rate in pick-and-place tasks. Some limitations were noted, such as reachability issues and minor positional errors.

## Conclusion and Future Work
The study successfully demonstrated the viability of using the Phantom X Pincher Arm for pick-and-place tasks with promising results in object detection and manipulation. Future work will focus on:
- Enhancing object detection and manipulation accuracy.
- Improving trajectory planning.
- Exploring intuitive control methods, such as reinforcement learning, for real-time robot guidance.

## References
1. [Industrial Robot History](https://www.robots.com/articles/industrial-robot-history)
2. [Peter Corke's Robotics Toolbox](https://petercorke.com/toolboxes/robotics-toolbox/)

## Digital Material
- GitHub Repository: [4 DOF Arm Manipulation](https://github.com/MHussainR/4_DOF_Arm_Manipulation)
- Videos of the Task: [Lab 7 & 8 Video](https://habibuniversity-my.sharepoint.com/personal/ma07534_st_habib_edu_pk/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Fma07534_st_habib_edu_pk%2FDocuments%2Fmy%20computer%2Fab%2F1%2EHabib%2Fsem%206%2FIntrotoRobotics%2Flabs%2Flab%208%2FLab7%20%26%208%20Video&ga=1*)

---

Happy Robotics!
