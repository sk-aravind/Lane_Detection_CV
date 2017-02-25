#**Finding Lane Lines on the Road** 
### Utilizing computer vision techniques and smoothing to detect lanes 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

![title](Pipeline_visualized.png)

## The pipeline 

1. Smoothing using gaussian blur 
2. Canny Edge detection 
3. Masking region of interest 
4. Hough Transform to identify lines
5. From Hough lines, calculate gradient of all lines 
6. Threshold lines to remove vertical lines 
7. Filter lines by positive and negative gradients to get left and right lines 
8. Calculate average gradient and b of longest n lines 
9. Get equation of line, find endpoints and plot on the image 
10. To increase stablitiy of lines under changing conditions, introduce smoothing , by averaging the last 10 frames

### White Lanes Video
[![Video White](https://github.com/sk-aravind/Lane_Detection_CV/blob/master/white.gif?raw=true)](https://github.com/sk-aravind/Lane_Detection_CV/blob/master/white.mp4)
### Yellow Lane Video
[![Video Yellow](https://github.com/sk-aravind/Lane_Detection_CV/blob/master/yellow.gif?raw=true)](https://github.com/sk-aravind/Lane_Detection_CV/blob/master/yellow.mp4)
### Challenge Video (optional)
[![Video Challenge](https://github.com/sk-aravind/Lane_Detection_CV/blob/master/extra.gif?raw=true)](https://github.com/sk-aravind/Lane_Detection_CV/blob/master/extra.mp4)

## Further Development 

* Curved Line Mapping 

    * Currently it can fit a line to a short section of the lane curve, but would like to develop a pipline that utilizes np.polyfit to fit the lane points to a second degree equation to get a more accurate mapping for curves. 


* Changes in Lighting Conditions and Lane-Marking Contrast

    * Utilizing Gamma correction we are able to normalize the image by a little and obtain more detail and hence more points to perform the hough detection on


* Color Stacking
    * Assuming you know the ranges of colors of the lane marking you could use color isolation to extract lane markings from the image and stack it against an the original darkned images to make the lanes even more pronounced.


* Parameter Finetuning 
    * To finetune parameters of hough transformation live to get better feedback instantaneously


* Deep learning 
    * lol


# Project Setup

**Step 1:** Getting setup with Python

To do this project, you will need Python 3 along with the numpy, matplotlib, and OpenCV libraries, as well as Jupyter Notebook installed. 

We recommend downloading and installing the Anaconda Python 3 distribution from Continuum Analytics because it comes prepackaged with many of the Python dependencies you will need for this and future projects, makes it easy to install OpenCV, and includes Jupyter Notebook.  Beyond that, it is one of the most common Python distributions used in data analytics and machine learning, so a great choice if you're getting started in the field.

Choose the appropriate Python 3 Anaconda install package for your operating system <A HREF="https://www.continuum.io/downloads" target="_blank">here</A>.   Download and install the package.

If you already have Anaconda for Python 2 installed, you can create a separate environment for Python 3 and all the appropriate dependencies with the following command:

`>  conda create --name=yourNewEnvironment python=3 anaconda`

`>  source activate yourNewEnvironment`

**Step 2:** Installing OpenCV

Once you have Anaconda installed, first double check you are in your Python 3 environment:

`>python`    
`Python 3.5.2 |Anaconda 4.1.1 (x86_64)| (default, Jul  2 2016, 17:52:12)`  
`[GCC 4.2.1 Compatible Apple LLVM 4.2 (clang-425.0.28)] on darwin`  
`Type "help", "copyright", "credits" or "license" for more information.`  
`>>>`   
(Ctrl-d to exit Python)

run the following commands at the terminal prompt to get OpenCV:

`> pip install pillow`  
`> conda install -c menpo opencv3=3.1.0`

then to test if OpenCV is installed correctly:

`> python`  
`>>> import cv2`  
`>>>`  (i.e. did not get an ImportError)

(Ctrl-d to exit Python)

**Step 3:** Installing moviepy  

We recommend the "moviepy" package for processing video in this project (though you're welcome to use other packages if you prefer).  

To install moviepy run:

`>pip install moviepy`  

and check that the install worked:

`>python`  
`>>>import moviepy`  
`>>>`  (i.e. did not get an ImportError)

(Ctrl-d to exit Python)

**Step 4:** Opening the code in a Jupyter Notebook

You will complete this project in a Jupyter notebook.  If you are unfamiliar with Jupyter Notebooks, check out <A HREF="https://www.packtpub.com/books/content/basics-jupyter-notebook-and-python" target="_blank">Cyrille Rossant's Basics of Jupyter Notebook and Python</A> to get started.

Jupyter is an ipython notebook where you can run blocks of code and see results interactively.  All the code for this project is contained in a Jupyter notebook. To start Jupyter in your browser, run the following command at the terminal prompt (be sure you're in your Python 3 environment!):

`> jupyter notebook`

A browser window will appear showing the contents of the current directory.  Click on the file called "P1.ipynb".  Another browser window will appear displaying the notebook.  Follow the instructions in the notebook to complete the project.  

**Step 5:** Complete the project and submit both the Ipython notebook and the project writeup

