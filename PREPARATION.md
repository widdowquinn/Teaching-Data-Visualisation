# PREPARATION.md

This document describes how to prepare your local environment so that Python libraries for the workshop are available, and you can complete the exercises. It would be best to ensure that this environment is in place and working before you attend the workshop.

## Clone this repository

To follow the instructions below without (too much) modification, clone this repository to your machine, and change directory to the repository root:

```
git clone git@github.com:widdowquinn/Teaching-Data-Visualisation.git
cd Teaching-Data-Visualisation
```

## If you're not using `Anaconda`:

### Python 3.5

We assume that you will be running a recent version of Python 3 - preferably Python 3.5. The instructions for installing this on your platform can be found at the official Python downloads page:

* Python downloads page: [https://www.python.org/downloads/](https://www.python.org/downloads/)

### `virtualenv`

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

### Activate the virtual environment

We will install data visualisation and manipulation packages within the virtual environment. Confirm that you are in the root directory of the repository, and activate the virtual environment `rdvw`:

```
source rdvw/bin/activate
```

### Quick installation

The Python library requirements are given in the `requirements.txt` file in the root directory of this repository. To quickly (without too much typing - it takes just as long otherwise) install all required libraries, use the following command at the terminal in your virtual environment:

```
pip install -r requirements.txt
```

### Less quick installation 

The instructions below describe how to install each of the Python libraries individually:

#### Install `scipy`

`SciPy` is a collection of open-source software for maths, science and engineering. To install `scipy`, run the following command from within the virtual environment:

```
pip install scipy
```

* `scipy` homepage: [https://www.scipy.org/](https://www.scipy.org/)

#### Install `matplotlib`

`Matplotlib` is an open-source 2D plotting library that is effectively a "base" library underpinning many Python data visualisatio libraries. To install, run the following command within your virtual environment:

```
pip install matplotlib
```

* `matplotlib` homepage: [http://matplotlib.org/](http://matplotlib.org/)

#### Install `pandas`

`pandas` is an open-source library that provides data structure and analysis tools, including R-like dataframes. To install, run the following command from within the virtual environment:

```
pip install pandas
```

* `pandas` homepage: [http://pandas.pydata.org/](http://pandas.pydata.org/)

#### Install `Jupyter`

`Jupyter` is an open-source notebook environment that allows creation and sharing of documents containing live code, with support for many languages (including Python, R and Julia) *via* kernels.

```
pip install jupyter
```

* Project Jupyter homepage: [http://jupyter.org/](http://jupyter.org/)

#### Install `Seaborn`

`Seaborn` is an open-source Python library built upon `matplotlib` that allows straightforward production of more complex graphics than the base `matplotlib` package. To install, use the following command in your virtual environment:

```
pip install seaborn
```

* `Seaborn` homepage: [http://web.stanford.edu/~mwaskom/software/seaborn/index.html](http://web.stanford.edu/~mwaskom/software/seaborn/index.html)

#### Install `ggplot`

`ggplot` is an open-source plotting library based on Hadley Wickham's Grammar of Graphics and the R `ggplot2` library. To install, run the following in your terminal under the virtual environment.

```
pip install ggplot
```

* `ggplot` homepage: [http://ggplot.yhathq.com/](http://ggplot.yhathq.com/)

#### Install `bokeh`

`bokeh` is an open-source library ased on Hadley Wickham's Grammar of Graphics for building interactive web visualisations of data using only Python.

```
pip install bokeh
```

* `bokeh` homepage: [http://bokeh.pydata.org/en/latest/](http://bokeh.pydata.org/en/latest/)