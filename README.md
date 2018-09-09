<div align="center">
    <img src=".github/Logo_main_black.png", width="300">
</div>

-----------------

| **`Linux`** |
|-------------|
|[![Build Status](https://travis-ci.org/CMU-Perceptual-Computing-Lab/openpose.svg?branch=master)](https://travis-ci.org/CMU-Perceptual-Computing-Lab/openpose)|

[OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) represents the **first real-time multi-person system to jointly detect human body, hand, and facial keypoints (in total 135 keypoints) on single images**.

<p align="center">
    <img src="doc/media/pose_face_hands.gif", width="480">
</p>

## Features
- **Functionality**:
    - **2D real-time multi-person keypoint detection**:
        - 15 or 18 or **25-keypoint body/foot keypoint estimation**. **Running time invariant to number of detected people**.
        - **2x21-keypoint hand keypoint estimation**. Currently, **running time depends** on **number of detected people**.
        - **70-keypoint face keypoint estimation**. Currently, **running time depends** on **number of detected people**.
    - **3D real-time single-person keypoint detection**:
        - 3-D triangulation from multiple single views.
        - Synchronization of Flir cameras handled.
        - Compatible with Flir/Point Grey cameras, but provided C++ demos to add your custom input.
    - **Calibration toolbox**:
        - Easy estimation of distortion, intrinsic, and extrinsic camera parameters.
    - **Single-person tracking** for further speed up or visual smoothing.
- **Input**: Image, video, webcam, Flir/Point Grey and IP camera. Included C++ demos to add your custom input.
- **Output**: Basic image + keypoint display/saving (PNG, JPG, AVI, ...), keypoint saving (JSON, XML, YML, ...), and/or keypoints as array class.
- **OS**: Ubuntu (14, 16), Windows (8, 10), Mac OSX, Nvidia TX2.
- **Others**:
    - Available: command-line demo, C++ wrapper, and C++ API.
    - CUDA (Nvidia GPU), OpenCL (AMD GPU), and CPU versions.



## Latest Features
- Sep 2018: [**Experimental single-person tracker**](doc/quick_start.md#tracking) for further speed up or visual smoothing!
- Jun 2018: [**Combined body-foot model released! 40% faster and 5% more accurate**](doc/installation.md)!
- Jun 2018: [**Python API**](doc/modules/python_module.md) released!
- Jun 2018: [**OpenCL/AMD graphic card version**](doc/installation.md) released!
- Jun 2018: [**Calibration toolbox**](doc/modules/calibration_module.md) released!
- Jun 2018: [**Mac OSX version (CPU)**](doc/installation.md) released!
- Mar 2018: [**CPU version**](doc/installation.md#cpu-version)!
- Mar 2018: [**3-D keypoint reconstruction module**](doc/modules/3d_reconstruction_module.md) (from multiple camera views)!

For further details, check [all released features](doc/released_features.md) and [release notes](doc/release_notes.md).



## Contents
1. [Latest Features](#latest-features)
2. [Results](#results)
3. [Installation, Reinstallation and Uninstallation](#installation-reinstallation-and-uninstallation)
4. [Quick Start](#quick-start)
5. [Output](#output)



## Results
### Body-Foot Estimation
<p align="center">
    <img src="doc/media/dance_foot.gif", width="360">
</p>

### Body, Face, and Hands Estimation
<p align="center">
    <img src="doc/media/pose_face.gif", width="360">
</p>

### 3-D Reconstruction Module
<p align="center">
    <img src="doc/media/openpose3d.gif", width="360">
</p>

### Body and Hands Estimation
<p align="center">
    <img src="doc/media/pose_hands.gif", width="360">
</p>

### Body Estimation
<p align="center">
    <img src="doc/media/dance.gif", width="360">
</p>



## Installation, Reinstallation and Uninstallation
**Windows portable version**: Simply download and use the latest version from the [Releases](https://github.com/CMU-Perceptual-Computing-Lab/openpose/releases) section.

Otherwise, check [doc/installation.md](doc/installation.md) for instructions on how to build OpenPose from source.



## Quick Start
Most users do not need the [OpenPose C++ API](#openpose-c-api), but they can simply use the basic [Demo](#demo) and/or [OpenPose Wrapper](#openpose-wrapper).

- **Demo**: To easily process images/video/webcam and display/save the results. See [doc/demo_overview.md](doc/demo_overview.md). E.g. run OpenPose in a video with:
```
# Ubuntu
./build/examples/openpose/openpose.bin --video examples/media/video.avi
:: Windows - Portable Demo
bin\OpenPoseDemo.exe --video examples\media\video.avi
```

- **Calibration toolbox**: To easily calibrate your cameras for 3-D OpenPose or any other stereo vision task. See [doc/modules/calibration_module.md](doc/modules/calibration_module.md).

- **OpenPose Wrapper**: If you want to read a specific input, and/or add your custom post-processing function, and/or implement your own display/saving, check the `Wrapper` tutorial on [examples/tutorial_wrapper/](examples/tutorial_wrapper/). You can create your custom code on [examples/user_code/](examples/user_code/) and quickly compile it with CMake when compiling the whole OpenPose project. Quickly **add your custom code**: See [examples/user_code/README.md](examples/user_code/README.md) for further details.

- **OpenPose C++ API**: See [doc/library_introduction.md](doc/library_introduction.md).

- **Adding an extra module**: Check [doc/library_add_new_module.md](./doc/library_add_new_module.md).

- **Standalone face or hand detector**:
    - **Face** keypoint detection **without body** keypoint detection: If you want to speed it up (but also reduce amount of detected faces), check the OpenCV-face-detector approach in [doc/standalone_face_or_hand_keypoint_detector.md](doc/standalone_face_or_hand_keypoint_detector.md).
    - **Use your own face/hand detector**: You can use the hand and/or face keypoint detectors with your own face or hand detectors, rather than using the body detector. E.g. useful for camera views at which the hands are visible but not the body (OpenPose detector would fail). See [doc/standalone_face_or_hand_keypoint_detector.md](doc/standalone_face_or_hand_keypoint_detector.md).

- **Library dependencies**: OpenPose uses default Caffe and OpenCV, as well as any Caffe dependency. The demos additionally use GFlags. It could easily be ported to other deep learning frameworks (Tensorflow, Torch, ...). Feel free to make a pull request if you implement any of those!



## Output
Output (format, keypoint index ordering, etc.) in [doc/output.md](doc/output.md).




