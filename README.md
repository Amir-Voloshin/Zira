# Amir Voloshin, Zira Computer Vision Developer Test 

## Introduction
In this assessment I train, validate, compiled, and optimize a tflite model with EfficientDet-Lite0 architecture for detecting boards in images and videos.
I initially had issues downloading the tflite-model-maker package on google colab because tflite-model-maker isn't compatible yet with python 3.10 which is the version used in google colab (I attempted to use the fallback runtime on colab to use an earlier version of python but fallback runtime was unavailable). Eventually I found a workaround which consists of creating a new virtual environment using conda (earlier version of python) within google colab, and writing a .py file with the necessary code to run in the virtual environment. 

A formal report of my code excluding code and videos is named 'CV Test Report.html'
## Code for parts 1-5 is in 'train.py'
### Part 1
Downloaded and imported the provided data and saved in train, validate, and test directories. Imported the data into python using the PASCAL VOC format function in tflite-model-maker.

### Part 2
Trained a model on the training data using efficientdet_lite0, a batch size of 4, and the default number of epochs (50).

### Part 3
Validated the trained model, obtained COCO Metrics from and validation data.

### Part 4
Compiled and saved my model as 'boards.tflite'.

### Part 5
Applied model quantization, configuring my model to float16 to improve performance. Additionally, I validated my model with the validation set and saved as 'quant.tflite'.

### Part 6
Performed model detection on the test set and 'video3.mp4'. Detection on the test set outputs a photo with a red rectangle surrounding the detected board for each photo in the test set while detection on the video has a green trailing rectangle among all boards which pass by. Detected images from test set are in the notebook and the video detection is in 'output_video.mp4'

### Extra
I decide to train and quantized an additional model with more epochs to achieve higher performance metrics (COCO), trained a new model with a batch size of 4 and 200 epochs. Code for this portion is in 'train_long.py'.
In addition I created a new video where this extra model is detecting boards, video saved as 'output_video_long.mp4'

