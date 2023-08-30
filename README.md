# Screwdriver Type Identification Project

This project uses AI and Machine Learning to identify what type of screwdriver is in an image from the main 4 types (Phillips, Flathead, Hex, and Torx). It does this using ImageNet to differentiate between each type and label each one differently.

![Screwdriver types are shown in this image:](https://i.imgur.com/XBAHT2q.png)

## The Algorithm

The Classification Algorithm works by using ImageNet, which takes an input image and outputs the image with a label of what class the AI thinks it is with a percentage representing the accuracy of the labeling. Furthermore, a labels.txt file is used to give names to the classes that the AI will use to classify each of the images, whether it's a live feed from a camera or a still image. The way ImageNet works is that it basically analyzes and connects similarities between images and puts them all under an umbrella, which is the label; it does this for each class.

## Running this project

## **Prerequisites**:
a Jetson Nano Developer Kit from NVIDIA is suggested, but alternatives exist. Images of screwdrivers for testing are required as well. You will also need an understanding of how Linux works.
## **Step 1**: 
Install git and cmake onto your board using the following commands:

***sudo apt-get update***

***sudo apt-get install git cmake***

## **Step 2**: 
Copy the jetson-inference repository from Github using these commands:

***git clone --recursive https://github.com/dusty-nv/jetson-inference***

***cd jetson-inference***

***git submodule update --init***

## **Step 3**: 
Install the Python packages using this command:

***sudo apt-get install libpython3-dev python3-numpy***

## **Step 4**: 
Make a directory that you will build your project into, *note that you must be in the jetson-inference directory when you use this command*:

***mkdir build***

## **Step 5**: 
Change directories into build and run cmake using these commands:

***cd build***

***cmake ../***

## **Step 6**: 
Inside the build directory, run these commands to finish installation:

***make***

***sudo make install***

***sudo ldconfig***

## **Step 7**: 
Download the labels.txt file and the model to the classification directory accessed by *cd jetson-inference/python/training/classification* (assuming you are not in jetson-inference already, otherwise it is *cd python/training/classification*), this is done by dragging and dropping labels and the model to classification (using Visual Studio Code).

## **Step 8**: 
Upload an image to the board by copying it from your computer to the board via terminal or using Visual Studio Code (dragging and dropping it), or have a live camera feed open. Run the project with the target image being the image you uploaded.

## **Step 9**: 
Use this command to run the program on your image:
*imagenet.py --model={**the directory with the model in it (should be "classification")**}/resnet18.onnx --input_blob=input_0 --output_blob=output_0* *--labels={**the directory with the model in it (should be "classification")**}/labels.txt* *{**location of the image (should be "classification" or the filepath to classification)**}* *{**output filepath/name, if it is in classification, just use the file name**}*

## **Step 10**: 
View the results by opening the image, the results will be displayed as a label of the class and the percentage of accuracy. The terminal will display the class and percentage of accuracy, but to view the actual image, you need to open the image itself from Visual Studio Code.


[View a video explanation here](video link)
