# Get Started

<a href="https://nbviewer.org/github/DreamPTK/yolov5/blob/master/detect.ipynb"><img src="https://user-images.githubusercontent.com/2791223/29387450-e5654c72-8294-11e7-95e4-090419520edb.png" alt="Open In nbviewer"></a>

## In Anaconda Prompt or the Terminal

    cd your_directory

### Creating new virtual environment
Create new folder name: "sign_project" on your directory. Put your own environment name instead of "envName" or you can you this name.

    mkdir sign_project
    cd sign_project
    python -m venv envName

### Activate your environment 

    envName\Scripts\activate.bat


<!-- ### Installation

    pip install ThTaxSigns -->


<!-- open new terminal (command line) -->

### Using Git clone to set up the model tools
[how to set up git click >>](https://stackpython.medium.com/%E0%B8%97%E0%B8%B3%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%A3%E0%B8%B9%E0%B9%89%E0%B8%88%E0%B8%B1%E0%B8%81-git-github-%E0%B8%9E%E0%B8%A3%E0%B9%89%E0%B8%AD%E0%B8%A1%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99%E0%B8%A3%E0%B9%88%E0%B8%A7%E0%B8%A1%E0%B8%81%E0%B8%B1%E0%B8%9A-vs-code-%E0%B9%80%E0%B8%9A%E0%B8%B7%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B9%89%E0%B8%99-f848f41a39e9)

```

git clone https://github.com/DreamPTK/yolov5.git

```
### Open Visual Studio Code (VScode)

```
code .

```


## In Visual Studio Code (VScode)

Open `detect.ipynb` on `yolov5` folder and

Open New Terminal in Vscode (command Prompt)

```
cd yolov5
pip install -qr requirements.txt  

```

### Import module and set up tools

In `detect.ipynb`

```
import os
import utils
display = utils.notebook_init()

```

### Detection Sign image

The `detect.py` run ThTaxSign model on all images source of `data/images` folder and save the result to `output/exp` folders.

This case study have two images source on `data/images` folder.

```
# use ThTaxSign model to detect 
!python detect.py --img 640 --weights ThTaxSigns/data/models.pt --conf 0.7  --source ThTaxSigns/data/images --project ThTaxSigns/data/output --save-crop

```
 `--img`: inference size (height, width)

`--weights`: model path or triton URL

`--conf`: confidence threshold

`--source`: file/dir/URL/glob/screen/webcam (source of the image)

`--project`: save results to project/name

`--save-crop`: save cropped prediction boxes

[Other option you can read more !!!](https://github.com/ultralytics/yolov5/blob/master/detect.py)



### Display output

First image

```
# display image
display.Image(filename='/content/yolov5/ThTaxSigns/data/output/exp/testimg2.jpg', width=600)

```

![123](img/testimg2.jpg)

Second image

```
# display image
display.Image(filename='/content/yolov5/ThTaxSigns/data/output/exp/testimg2.jpg', width=600)

```

![123](img/testimg3.jpg)



### Display crop output

This tool will separatly crop the sign image output to several image files.

```
from IPython.display import display, Image

def display_images_from_folder(folder_path):
    # List all files in the folder
    files = os.listdir(folder_path)
    
    # Filter out only image files
    image_files = [file for file in files if file.endswith(('.jpg', '.jpeg', '.png', '.gif'))]
    
    # Display each image
    for image_file in image_files:
        image_path = os.path.join(folder_path, image_file)
        display(Image(filename=image_path, width=300))

```

```
folder_path = "E:/test/sign_project/yolov5/ThTaxSigns/data/output/exp/crops/unidentified_signs"

display_images_from_folder(folder_path )

```

![123](img/testimg_crop.jpg)

![123](img/testimg31.jpg)

![123](img/testimg32.jpg)

![123](img/testimg33.jpg)


You can see these crop image outputs on `output/exp/crops/unidentified_signs` folder
