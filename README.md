# YOLOv2 Object Detection with Keras
This repo uses YOLO version 2 with Keras to detect objects in videos.

## A brief overview of Algorithm:
- Give a video as the input
- Break the video into Frames
- For simplicity, we are taking 0.5 frames per second
- Divide each frame(image) using  grids
- Perform image classification and Localization on each grid cell -> Result, a vector for each cell representing the probability of an object detected, the dimensions of the bounding box and class of the detected image.
- Perform thresholding to remove multiple detected instances
- Perform Non-max suppression to refine the boxes more
- Additionally anchor boxes are used to detect several objects in one grid cell
- Combine the processed images (again with 0.5 frames per second) and make a video


--------------------------------------------------------------------------------

## Quick Start

- Clone this repository to your PC
- Create your virtual environment ```virtualenv object_det```
- Activate your virtual environment ```source object_det/bin/activate```
- Install dependencies from requirement.txt ```pip install --user --requirement requirements.txt```
- Install OpenCV
- Place your video in the master directory
- Change the input/output paths specific to your system
- Download pre-trained YOLO cfg and weights files from https://pjreddie.com/darknet/yolo/ 
- Convert the dowloaded cfg and weights files into a h5 file using YAD2K library. (This is explained step by step below in the more details section)
- Copy the generated h5 file to the model_data folder and edit the name of the pretrained model in yolo.py code to the name of your h5 file.
- Assign your input image file name to input_image_name variable in yolo_video.py.
- Open terminal from the repository directory directly and run the yolo_video.py file

	`python yolo_video.py`

--------------------------------------------------------------------------------

## How to get weights
How to convert cfg and weights files to h5 using YAD2k library (Windows)

- Clone the YAD2K Library to your PC
- Open terminal from the cloned directory
- Copy and paste the downloaded weights and cfg files to the YAD2K master directory
- Run python yad2k.py yolo.cfg yolo.weights model_data/yolo.h5 on the terminal and the h5 file will be generated.
- Move the generated h5 file to model_data folder of the simpleYOLOwKeras directory
- I have used YOLOv2 608x608

----------------------------------------------------------------------------------

## For image processing

Use ``` python yolo.py``` command for detecting objects in a Image
