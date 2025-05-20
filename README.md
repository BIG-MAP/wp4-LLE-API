# LLE API

This is the source code of the LLE API

## Cloning
To download the source code install git on your computer. It can be downloaded [here](https://git-scm.com/download/win). Open a terminal in Linux or the GIT CMD program in Windows, navigate to an appropriate folder, and run the following command:

`git clone {url-of-this-github-repository}`

## Installation

To install the API, open a terminal in Linux or a command line in Windows and navigate to the folder containing this README file (use the `cd` command).

1. Python:

Install the latest version of the Python interpreter in your system (currently 3.11). It can be downloaded [here](https://www.python.org/downloads/).
In Windows: If not added automatically remember to add the Python executable folder to the Windows PATH library, both locally and systemwide if possible.

3. Poetry:

Install the latest version of Poetry in your system. It can be downloaded [here](https://python-poetry.org/docs/).
In Windows: If not added automatically remember to add the Poetry executable folder to the Windows PATH library, both locally and systemwide if possible.

4. Install dependencies:

From the Software folder run the following command to install all dependency libraries:

`poetry install`

## Running
To run the API after installing it, open a terminal in Linux or a command line in Windows and navigate to the folder containing this README file (use the `cd` command). Run the following command:

`poetry run lle-fastapi`

The API will check if all devices are connected, initialize them and fail otherwise. After a successful initialization the API will be running attached to the IP address of the computer it is running on, on port 8000.

To stop the API press CTRL-C in the command line window the API is running on. The API will automatically shut down.

## Updating

To update the API, stop it, open a terminal in Linux or the GIT CMD program in Windows, navigate to the folder containing this README file (use the `cd` command), and run the following command:

`git pull`

# Data

This repository also contains the data obtained for the paper *Movable optical sensor for automatic detection and monitoring of liquid-liquid interfaces* submitted to the SLAS Technology Journal.

# General Description

The software is divided into various parts:

- A set of drivers for controlling the arduino boards in the two LLE main components. These are based on the CmdMessenger [library](https://github.com/thijse/Arduino-CmdMessenger) and its PyCmdMessenger [counterpart](https://github.com/harmsm/PyCmdMessenger) and can be found under the Drivers folder in the BeltSensorCmd and DrainingAndRotaryCmd folder. Both a .ino and a .py files are included. A driver for the Tubing sensor and the camera can also be found in the Drivers folder.

- A set of python functions managing the main LLE procedures. These can be found in the API/FastAPI/LLEBeltDrainProcedures.py file and makes calls to the drivers. Functions for detecting the interface (findInterface), scanning the funnel (scanFunnel), as well as more specific functions for ruuning the pumps are included here.

- An API based on the FastAPI [library](https://fastapi.tiangolo.com/) that can be found in the API/FastAPI/BeltDrainLLE.py file. This file contains the main configuration and endpoints and calls the procedures in LLEBeltDrainProcedures.py. Documentation for this API can be accesed by launching the API and getting to the /docs resource in an internet browser.



