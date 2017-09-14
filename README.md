
### Sefl-Driving Car Nanodegree Program. Term 1
___

Author: Efraim Kropp (efraim.kropp@flex.com)

Date: 09/14/2017
___

# **Project 1: Finding Lane Lines on the Road** 

<img style="float: left;" src="examples/laneLines_thirdPass.jpg" width="480"  height="270" alt="Combined Image" style="max-width:100%;">

### **Overview**

When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. In this project we automatically detect lane lines in images using [Python](https://www.python.org/) and [OpenCV](http://opencv.org/). We use [Jupiter Notebook](http://jupyter.org/) to write and execute [Python](https://www.python.org/) code and [Anaconda](https://docs.anaconda.com/) to configure the enviroment for running the code.

In the project directory you can find [CarND_writeup_P1.md](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/CarND_writeup_P1.md) document explaining the solution.  

### Project directory content:

* [README.MD](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/README.MD) - this file
* [CarND_writeup_P1.md](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/CarND_writeup_P1.md) ([.html](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/CarND_writeup_P1.html), [.ipynb](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/CarND_writeup_P1.ipynb)) - project writeup
* [P1.md](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/P1.md) ([.html](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/P1.html), [.ipynb](https://github.com/ek8203/CarND-LaneLines-P1/blob/master/P1.ipynb)) - the actual project code with the solution
* *test_images/* - folder with the images to be tested
* *test_images_output/* - folder with output images after processing
* *test_videos/* - folder with videos to be tested
* *test_videos_output/* - folder with output videos after processing


** *NOTE:* ** HTML files and videos should be downloaded or **git clone** [the project repository on GitHub](https://github.com/ek8203/CarND-LaneLines-P1) before reading/playing

### Instructions for running the code on Windows

1. Install [Python3](https://www.python.org/) and [Anaconda](https://docs.anaconda.com/)
2. Setup and activate *carnd-term1* environment. In the Anaconda Prompt go to your home directory and run commands:  
 __git clone https://github.com/udacity/CarND-Term1-Starter-Kit.git   
 cd CarND-Term1-Starter-Kit   
 conda env create -f environment.yml   
 activate carnd-term1
 cd %homepath%__   
3. Get the project from Git:   
 __git clone https://github.com/ek8203/CarND-LaneLines-P1
 cd CarND-LaneLines-P1__
4. Launch *P1.ipynb* notebook:   
 __jupyter notebook P1.ipynb__
