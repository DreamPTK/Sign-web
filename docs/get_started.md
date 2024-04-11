# Get Started

<!-- ## Godream (Geo-dream)
Godream (Geo-dream) is a library that contain geospatial tools for RS&GIS analyze or geospatial analyze in python language. This appears to be a Python library specifically developed to assist in the analysis of geospatial data, with a focus on remote sensing and GIS applications. Such a library would likely provide functions and tools to manipulate, process, and visualize geospatial data, making it easier for users to perform complex analyses in these domains [pypi.org](https://pypi.org/project/Godream/).

[(How to create new environment)](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands) -->

## In Command line (CMD)
### Creating virtual environment
Create new folder name: "sign_project". Put your environment name instead of "envName".

    mkdir sign_project
    cd sign_project
    python -m venv envName

### Activate your environment 

    envName/Scripts/activate.bat


### Installation

    pip install ThTaxSigns


### Launch Visual Studio Code (VScode)

    code .

## In Visual Studio Code (VScode)

### Import libraries

```python
import Godream
from Godream.plotimg import show_map 
```

### Create an intercative map

```python
show_map()
```


<!-- ## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files. -->
