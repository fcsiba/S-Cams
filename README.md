# S-Cams
FYP Fall 2018:
Now a days, banks and other firms want to strengthen their security system. Whether by increasing the human resource or by improving the technical resource. Therefore, we have completely redesigned the concept of monitoring by introducing the S-Cam. We aim to provide a comprehensive introduction to the video-based human activity recognition. In which the camera needs to find a human in image frames. The body pose is classified for the detected human. Then the human activity is recognized by combining information of human pose, human location and elapsed time. 
Basically, using the S-Cam, cameras in firms will be integrated with our software. And whenever the suspicious activity is performed, the software will automatically detect it as a threat and will start alarming the security.
In a country like Pakistan, where the street crimes are increasing rapidly, everybody wants to be secure. The main motivation for us is to ensure that all financial firms are being run in a secure environment. Especially in banking sector. According to a research 1 in 3 bank robberies is carried out by a repeat offender. So, we believe in “Deter and Detect criminals before they act” 
S-Cam can stop fraud, robbery and violent crime before it even starts.

Working:
This system for recognizing human activities given a symbolic representation of video content. The input of this system is a stream of time-stamped short-term activities detected on video frames. The output of this system is a set of recognized long-term activities, which are pre-defined spatio-temporal combinations of short-term activities. The constraints on the short-term activities that, if satisfied, lead to the recognition of a long-term activity, are expressed using a dialect of the Event Calculus.

Requirements
Python 3.4+
TensorFlow 1.3+
Keras 2.0.8+
Jupyter Notebook
Numpy, skimage, scipy, Pillow, cython, h5py

MS COCO Requirements:
To train or test on MS COCO, you'll also need:
pycocotools (installation instructions below)
MS COCO Dataset
Download the 5K minival and the 35K validation-minus-minival subsets. More details in the original Faster R-CNN implementation.
If you use Docker, the code has been verified to work on this Docker container.

Setup Instructions:

In the command terminal that pops up, create a new virtual environment called “tensorflow1” by issuing the following command:
```
C:\> conda create -n tensorflow1 pip python=3.5
```
Then, activate the environment by issuing:
```
C:\> activate tensorflow1
```
Install tensorflow-gpu in this environment by issuing:
```
(tensorflow1) C:\> pip install --ignore-installed --upgrade tensorflow-gpu
```
Install the other necessary packages by issuing the following commands:
```
(tensorflow1) C:\> conda install -c anaconda protobuf
(tensorflow1) C:\> pip install pillow
(tensorflow1) C:\> pip install lxml
(tensorflow1) C:\> pip install Cython
(tensorflow1) C:\> pip install jupyter
(tensorflow1) C:\> pip install matplotlib
(tensorflow1) C:\> pip install pandas
(tensorflow1) C:\> pip install opencv-python
```
(Note: The ‘pandas’ and ‘opencv-python’ packages are not needed by TensorFlow, but they are used in the Python scripts to generate TFRecords and to work with images, videos, and webcam feeds.)

#### 2e. Configure PYTHONPATH environment variable
A PYTHONPATH variable must be created that points to the \models, \models\research, and \models\research\slim directories. Do this by issuing the following commands (from any directory):
```
(tensorflow1) C:\> set PYTHONPATH=C:\tensorflow1\models;C:\tensorflow1\models\research;C:\tensorflow1\models\research\slim
```
(Note: Every time the "tensorflow1" virtual environment is exited, the PYTHONPATH variable is reset and needs to be set up again.)

#### 2f. Compile Protobufs and run setup.py
Next, compile the Protobuf files, which are used by TensorFlow to configure model and training parameters. Unfortunately, the short protoc compilation command posted on TensorFlow’s Object Detection API [installation page](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md) does not work on Windows. Every  .proto file in the \object_detection\protos directory must be called out individually by the command.
