# PREPARATION.md

This document describes how to prepare your local environment so that Python libraries for the workshop are available, and you can complete the exercises. It would be best to ensure that this environment is in place and working before you attend the workshop.

## Clone this repository

To follow the instructions below without (too much) modification, clone this repository to your machine, and change directory to the repository root:

```
git clone git@github.com:widdowquinn/Teaching-Data-Visualisation.git
cd Teaching-Data-Visualisation
```

## Run the repository exercises

### 1. In your browser with `MyBinder`

These workshop materials are designed to be compatible with [MyBinder](mybinder.org). To start an instance of this repository, click on the badge below:

[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/widdowquinn/Teaching-Data-Visualisation)

### 2. `Anaconda`

We assume that you already have the most recent (or recently-updated) version of Anaconda available. This will enable you to create a new environment to run these exercises, using the following command from within the `Teaching-Data-Visualisation` directory:

```
conda env create -f environment.yml -n rdvw_conda
```

This will take some time to install the Anaconda libraries, and those additional libraries required for the exercises. Once it is complete, you can then use this environment with

```
source activate rdvw_conda
```

Your shell prompt will then alert you that you are working within the `rdvw-conda` environment:

```
$ source activate rdvw_conda
(rdvw_conda) $
```

To exit the environment, use:

```
source deactivate
```

and again your prompt will alert you that you have left the environment:

```
(rdvw_conda) $ source deactivate
$
```


### 3. Python `virtualenv`

We assume that you will be running a recent version of Python 3 - preferably Python 3.5. The instructions for installing this on your platform can be found at the official Python downloads page:

* Python downloads page: [https://www.python.org/downloads/](https://www.python.org/downloads/)

#### `virtualenv`

`virtualenv` is a tool that creates isolated Python environments. Using this means that we can install packages specific to this workshop, and not interfere with your existing Python setup. It is like having a new, "clean" Python installation.

* `virtualenv` documentation: [https://virtualenv.pypa.io/en/stable/](https://virtualenv.pypa.io/en/stable/)

#### Installation

You can install or upgrade `virtualenv` with the `pip` installation tool (if this is installed):

```
pip install --upgrade pip
pip install --upgrade virtualenv
```

#### Creating a virtual environment for this workshop

The command `virtualenv` creates a new virtual environment in the current working directory, containing a version of Python that is isolated from your system-level Python installation.

Firstly, ensure that you are in the root directory of this workshop repository, in your terminal. Then use `virtualenv` to create a new virtual environment called `rdvw`:

```
virtualenv ./rdvw
```

This will create a new subdirectory called `rdvw` containing a "clean" Python installation:

```
$ tree rdvw -L 2
rdvw
├── bin
│   ├── activate
│   ├── activate.csh
│   ├── activate.fish
│   ├── activate_this.py
│   ├── easy_install
│   ├── easy_install-3.5
│   ├── pip
│   ├── pip3
│   ├── pip3.5
│   ├── python -> python3.5
│   ├── python-config
│   ├── python3 -> python3.5
│   ├── python3.5
│   └── wheel
├── include
│   └── python3.5m -> /usr/local/Cellar/python3/3.5.1/Frameworks/Python.framework/Versions/3.5/include/python3.5m
├── lib
│   └── python3.5
└── pip-selfcheck.json
```

#### Activating the virtual environment

To use the new virtual environment, you must explicitly *activate* it by running the `activate` shell script:

```
source rdvw/bin/activate
```

You should notice that your command-line prompt changes to indicate that you are now working in the `rdvw` virtual environment, by placing the indicator `(rdvw)` at the start of the prompt, e.g.:

```
lpritc@Totoro:2016-07-28_manchester_datavis$ source rdvw/bin/activate
(rdvw) lpritc@Totoro:2016-07-28_manchester_datavis$ 
```

#### Leaving the virtual environment

To exit the virtual environment, and return to using the system Python, use the `deactivate` command:

```
deactivate
```

As before, your shell prompt should change to alert you that you are no longer within the virtual environment `rdvw`:

```
(rdvw) lpritc@Totoro:2016-07-28_manchester_datavis$ deactivate
lpritc@Totoro:2016-07-28_manchester_datavis$ 
```

#### Activate the virtual environment

We will install data visualisation and manipulation packages within the virtual environment. Confirm that you are in the root directory of the repository, and activate the virtual environment `rdvw`:

```
source rdvw/bin/activate
```

#### Quick installation

The Python library requirements are given in the `requirements.txt` file in the root directory of this repository. To quickly (without too much typing - it takes just as long otherwise) install all required libraries, use the following command at the terminal in your virtual environment:

```
pip install -r requirements.txt
```