
# **Finding Lane Lines on the Road** 

## Project 1 Writeup

### (This writeup document is created based on the "writeup_template.md" template)
---

## Goals:

* Make a pipeline that finds lane lines on the road
* Write a report reflecting the work
---

### Reflection

#### 1. Pipeline description

My pipeline is using the basic tools learned in Lesson 1 of the course to identify lane lines on the road. Those tools are:
* Color selection
* Region of interest selection
* Grayscaling 
* Gaussian smoothing 
* Canny Edge Detection and 
* Hough Tranform line detection

First I tested the pipeline process on the provided test images. I put the image filenames in a list to read them in a loop and simulate the pipeline. In the loop I was reading a image  from file and called a function ***proc_img_pipe*** to process the image.
In the function I grayscaled the image and applied Gaussian filter to smooth the image. Then I detected the edges of the objects by applying Canny agrorithm. In order to isolate the lane lines on the road I mask out a region of interest by defining vertices that form a poligon mask on the image. I used the resulting masked image as an input for Hough transform that gave me an image of the lane lines as an output. The I blended the lines with the original image and save the result image as file in the output directory.

The below are tested images with the lines after processing:

![image.png](attachment:image.png)

* Modification of the **draw_lines()** function

Extending the lines on the image in the ***draw_lines()*** function required an additional effort and was challenging. After several attempts I choosed to simple extrapolation of the lines to the bottom of the image using line slope m = ((y2-y1)/(x2-x1)) and the end points of source lines. The result code looks like following:

```python
    # Extend lines by simple extrapolation to the bottom of the image
    for line in lines:
        for x1, y1, x2, y2 in line:
            if (x2 - x1):
                m = (y2 - y1)/(x2 - x1)
                if m != 0:
                    if y1 > y2:
                        y1 = bottom_start
                        x1 = int(x2 - (y2 - y1)/m)
                        cv2.line(img, (x1, y1), (x2, y2), color, thickness)
                    else:
                        y2 = bottom_start
                        x2 = int(x1 + (y2 - y1)/m)
                        cv2.line(img, (x1, y1), (x2, y2), color, thickness)
```
where *bottom_start* is the Y-size of the original image passed to the function as an argument


* Testing the videos

After verifying the pipeline on the test images I included ***proc_img_pipe*** function call in the template function ***process_image*** to test it on the provided videos. The result output videos were save in the *"test_videos_output/"* directory (to be embedded after getting GitHub account)

As tested the Challenge video does not work with my pipeline 


#### 2. Potential shortcomings with my pipeline

My pipeline has few shortcomings.

First it does not work with the challenge video and it required additional effort and time to figure out how to fix the issues. 

Second my extrapolation of the line is very rough and requires some more processing like averaging and filtering.

#### 3. Possible improvements to my pipeline

Possible improvement to my pipeline would be adding averaging and filtering in the ***draw_lines()*** function

Potencial improvement would be making modification to solve the challenge video issues. I guess the camera on the vehicle was a little off but have no idea how to approach that in the software. Maybe redefining the regeon in run-time could fix it but it sounds too soficticated to implement.
