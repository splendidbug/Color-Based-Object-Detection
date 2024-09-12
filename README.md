C++ Color Based Object Detection
======

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/RocketChat/Rocket.Chat/raw/master/LICENSE)
![language](https://img.shields.io/badge/language-c++-blue.svg)
![c++](https://img.shields.io/badge/std-c++14-blue.svg)

## Overview
This is an object detection which detects the objects purely based on color. It draws a bounding box around the detected object and prints the name of the object.

## Installations
- Install [gcc compiler](https://gcc.gnu.org/gcc-14/)
- `git clone https://github.com/splendidbug/Color-Based-Object-Detection-.git`
## Usage
`Image.exe path_to_image path_to_object1, path_to_object2, ...`

## Sample Input
`Image.exe resources\multi_object_test_new\update_rgb\Oswald_and_Volleyball_v2.rgb resources\dataset\data_sample_rgb\Oswald_object.rgb resources\dataset\data_sample_rgb\Volleyball_object.rgb`

## Output
1. Identifying Oswald and a volley ball. Draws a bounding box around both the objects with the object name.

![Alt text](Assets/output1.png?raw=true "Title")

2. Identifying Pikachu. Draws a bounding box around both the objects with the object name.

![Alt text](Assets/output2.png?raw=true "Title")

## Methodology
1. First the RGB input image and objects are converted into HSV color space.
2. After this, color ranges in object image are identified and weights are assigned where a color range is given more weight if more number of pixels fall in the color range. These weights and colors are corrosponed with that of the input image.
3. Once the colors and weights are identified, a mask is built on the stipulated area where the object is present.
4. This is mask is then reduced in size to match the aspect ratio of the object in the object image.
5. A bounding box is created and the name of object is assigned 
