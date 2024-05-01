# Get Started

<a href="https://colab.research.google.com/drive/1dtr-IVnMX3Xy-vTf-p4Kmy2Zobk0CZtq?usp=sharing"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

## In Anaconda Prompt

    cd your_directory

### Creating virtual environment
Create new folder name: "sign_project" on your directory. Put your own environment name instead of "envName".

    mkdir sign_project
    cd sign_project
    python -m venv envName

### Activate your environment 

    envName\Scripts\activate.bat


<!-- ### Installation

    pip install ThTaxSigns -->


### Launch Visual Studio Code (VScode)

    code .

## In Visual Studio Code (VScode)

open new terminal (command line)

### Using Git clone to set up the model tools
[how to set up git click >>](https://stackpython.medium.com/%E0%B8%97%E0%B8%B3%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%A3%E0%B8%B9%E0%B9%89%E0%B8%88%E0%B8%B1%E0%B8%81-git-github-%E0%B8%9E%E0%B8%A3%E0%B9%89%E0%B8%AD%E0%B8%A1%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99%E0%B8%A3%E0%B9%88%E0%B8%A7%E0%B8%A1%E0%B8%81%E0%B8%B1%E0%B8%9A-vs-code-%E0%B9%80%E0%B8%9A%E0%B8%B7%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B9%89%E0%B8%99-f848f41a39e9)

```
# clone yolov5
!git clone https://github.com/DreamPTK/yolov5.git

# cd to yolov5
%cd yolov5

# clone ThTaxSign
!git clone https://github.com/DreamPTK/ThTaxSigns.git

# install
%pip install -qr requirements.txt  

```

open detect.ipynb on yolov5 directory

### Import module and set up tools

```
%cd yolov5

import utils
display = utils.notebook_init()

```

### Detection Sign image

`detect.py` run ThTaxSign model on images source and save the result to `output/exp`

```
# use ThTaxSign model to detect 
!python detect.py --img 640 --weights /content/yolov5/ThTaxSigns/data/model/model.pt --conf 0.5  --source /content/yolov5/ThTaxSigns/data/images --project /content/yolov5/ThTaxSigns/data/output --save-crop

```
 `--img`: inference size (height, width)

`--weights`: model path or triton URL

`--conf`: confidence threshold

`--source`: file/dir/URL/glob/screen/webcam (source of the image)

`--project`: save results to project/name

`--save-crop`: save cropped prediction boxes

[Other option read more !!!](https://github.com/ultralytics/yolov5/blob/master/detect.py)



### Display output

```
# display image
display.Image(filename='/content/yolov5/ThTaxSigns/data/output/exp/testimg2.jpg', width=600)

```

![123](img/testimg2.jpg)

### Display crop output

```
# display crop images
display.Image(filename='ThTaxSigns/data/output/exp/crop', width=600)

```




