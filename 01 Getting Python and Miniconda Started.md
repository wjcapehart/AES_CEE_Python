# Getting the Stuff to Get Started

## HURRY-UP AND WAIT!

Installing Python can take a while.  Much of it is spent letting the package manager to 

## 1 Installing Miniconda

I am recommending that you use Miniconda for this.  Minoconda is a "slimmed down" version of the larger Anaconda package that many people recommend.  My experience is that the overhead for Anaconda makes for lots of problems later. The instructions to get Miniconda installed on Windows or MacOS is here:     

*  [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html).

## 2 Adding and Locking-down Conda-Forge as your designated channel

Also, I am recommending that you work mostly through the conda-forge community.  Again, this provides more consistency in a lot of the packages with which you'll be working. There are scores of repository areas (or "channels" in the conda community). Consequently, it is easy to accidentally get a package that was written by Frank that relies on a package written by Susan, which (naturally) is reliant on one developed by Pat.  The result can be a web of dependencies that may eventually conflict once you install "that one package."  Therefore we will stick with conda-forge as the "go-to" channel to get your packages.  From my experience, it's provided the least amount of misery.  

To enable conda-forge, you should open a terminal window (in Unix or Mac, it's just a terminal window), and in Windows, you can find an "Anaconda Powershell" that will drop you into a conda-friendly operating system environment.

Once you have an open working terminal, enter the following commands one line at a time.

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Then run an update to set this channel's packages as *your* packages.

```warning
The late August 2023 installation of Miniconda gave me some rather odd errors when installing. I have revised the script below to reflect that.  Also, this semester's installation takes much longer on my Windows machine than in the past.  Times on the mac will vary.
```

```
conda update -c conda-forge --all
conda update -c conda-forge conda
```

## 3 Loading some Libraries.

### 3.1 Commonly-Used Libraries

I recommend that, at this point, you load several libraries and packages.

First, you will need the Jupyter Resource packages to get the Jupyter notebooks running.

* [Jupyter Notebooks, and JupyterLab](https://jupyter.org) and [IPython](https://ipython.org) environments
  * These are the jupyter, jupyterlab, and notebook packages.  This will also include the IPython interactive python environment

Then you can install (or reinstall) the following basic "must-have" packages for working in data science.

* [NumPy](https://numpy.org) The go-to package for basic math, array, and matrix handling with Python
* [Matplotlib](https://matplotlib.org) The go-to package for graphics and plotting in Python
* [SciPy](https://www.scipy.org) A library used for scientific computing and technical computing
* [Pandas](https://pandas.pydata.org) A package commonly used for working with tabular data as well as time series data
* [SymPy](https://www.sympy.org/en/index.html) An symbolic algebraic solver engine for Python
* [Scikit-Learn](https://scikit-learn.org/stable/) An open-source set of libraries for regressions, cluster analyses, and similar "machine-learning" activities.
* [seaborn](https://seaborn.pydata.org) An extension to Matplotlib for graph customization and more fancy graphics (often tied to statistical-type graphs.
* [openpyxl](https://openpyxl.readthedocs.io/en/stable/) A Python library to read/write Excel 2010 xlsx/xlsm files
* [pyreadr](https://github.com/ofajardo/pyreadr#pyreadr) A Package to read and write R RData and Rds files into/from pandas dataframes

In your terminal window, enter the following *one line at a time*:

```
conda install -c conda-forge jupyterlab  
conda install -c conda-forge numpy matplotlib scipy sympy pandas xarray
conda install -c conda-forge scikit-learn seaborn openpyxl pyreadr
```

```warning
When installing with conda it will first try to reconcile all the packages so any given package doesn't have components that may "break" other packages.  This you may get a warning saying that the "solving environment" has failed and it's trying another set of requirements.

You may also experience a few iterations of "Solving Environment," as shown below.

```
![Conda Struggling to Reconcile Packages](images/Conda_Struggling_to_Reconcile_Packages.png) 




### 3.2 More specialized libraries (not needed for CEE 284 students but students wanting to work in Atmospheric Sciences will want some of these)
If you are working in any of the hydrology, weather & climate groups, you will also want to install the following.

* Get the following mapping libraries
  * [Cartopy](https://scitools.org.uk/cartopy/docs/latest/) A basic geospatial processing library that will be essential for mapping
  * [Shapely](https://shapely.readthedocs.io/en/latest/) A support package to help manipulate geometric objects
  * [OWSLib](https://geopython.github.io/OWSLib) Access to the Open Geoscience Consortium resources and services.  Lots of good mapping goodies to have.
  * [pyProj](https://pyproj4.github.io/pyproj/stable/) An interface for working with map projections
  * [geopandas](https://geopandas.org/en/stable/) Geospatial access that leverages Pandas's Dataframe style resources

* Get the following complex data and meteo data resources
  * [xarray](http://xarray.pydata.org/en/stable/) Data manipulation and archiving of multi-dimensional datasets
  * [pint](https://pint.readthedocs.io/en/stable/) and [pint-xarray](https://pint-xarray.readthedocs.io/en/latest/) units support
  * [metpy](https://unidata.github.io/MetPy/latest/index.html) UCAR-Unidata tools for reading, viewing, and analyzing meteo data
  * [netCDF4](https://unidata.github.io/netcdf4-python/) UCAR-Unidata tools for NetCDF4 Support
  * [Siphon](https://unidata.github.io/siphon/latest/) UCAR-Unidata support for accessing remote meteo data
  * [pyGrib](https://jswhit.github.io/pygrib/) NOAA-ESRL tools for WMO Gridded Binary (GRIB 1/2) support
  * [cfGrib](https://github.com/ecmwf/cfgrib) ECMWF tools for WMO Gridded Binary (GRIB 1/2) support
  * [cftime](https://unidata.github.io/cftime/) UCAR-Unidata support for time data support (including 360-day, leap-year-free 365-day, and other quirky calendars, that only a meteorologist would love because the rest of the world are monsters)
  * [cf-python](https://ncas-cms.github.io/cf-python/) an Earth science data analysis library that is built on a complete implementation of the CF data model
  * [cf-plot](http://ajheaps.github.io/cf-plot) a set of Python routines for making the common contour, vector, and line plots that climate researchers use
  * [cf-units](https://cf-units.readthedocs.io/en/latest/) Provision of a wrapper class to support Unidata/UCAR UDUNITS-2, and the cftime calendar functionality
  * [timezonefinder](https://timezonefinder.readthedocs.io/en/latest/) useful for converting from civilized UTC time to more vulgar local times (including "daylight-'savings'" time).
  * [pytz](http://pytz.sourceforge.net) further support for time zones
  * [haversine](https://github.com/mapado/haversine) Calculate the distance (in various units) between two points on Earth using their latitude and longitude.
  * [wrf-python](https://wrf-python.readthedocs.io/en/latest/) A collection of diagnostic and interpolation routines for use with output from the Weather Research and Forecasting (WRF-ARW) Model.
  * [iris](https://scitools-iris.readthedocs.io/en/stable/) A powerful, format-agnostic, community-driven Python package for analysing and visualising Earth science data 


```
conda install -c conda-forge shapely cartopy OWSLib pyproj geopandas
conda install -c conda-forge pint pint-xarray pint-pandas metpy netCDF4 
conda install -c conda-forge siphon cfgrib pygrib timezonefinder 
conda install -c conda-forge cftime cfdm wrapt setuptools cython
conda install -c conda-forge pytz haversine cf-units
conda install -c conda-forge iris satpy
conda install -c conda-forge basemap-data basemap-data-hires
```

```warning
WRF-Python and Basemap for Apple Silicon machines have been temporarily removed from conda-forge, so proceed cautiously.
```

```
conda install -c conda-forge wrf-python 
conda install -c conda-forge basemap 
```

## 4 Get Git (If you don't already have it).

Git is a revision-control program and environment that accesses code repositories made public to the larger user community. If you have a Mac, you already have it in the MacOS operating system.  If you are in Windows, you can get it from your terminal window by typing the following command.

```
conda install -c conda-forge git
```

## 5 Adding a library that we'll be using: "version_information"

Conda and Conda-Forge have many libraries that we'll be using.  But we will be needing one more that doesn't always come in with the default distribution of Python.  *"Version_Information"* is a tool to extract information on the modules, operating system, and other resources used in any Juptyer Notebook Python session.  Currently, the Version_Information is not compatible with the current release of Python.  Robert Johansson, the original author of the package, no longer supports it, but since it has a cult following (including me!), some of us have been trying to maintain it.

You can access it using the terminal window:

```
pip install git+https://github.com/wjcapehart/version_information
```
## 6 "Let's Light This Candle!"

How we are ready to go.  To launch Jupyter, I recommend that you again open the Anaconda Powershell Prompt from the start menu if it's not open already. You can also "Pin" it to your "Start" for easy access along with Excel and Mathcad.)

At the shell prompt, enter. 

```
jupyter lab
```

And then the fun starts...

### 6.1 Firing Up the Jupyter Service

... the first thing you will see is a flurry of activity in your shell window.  That's ok.  What is happening is that your laptop is creating a virtual web service.   

!["My God! It's full of text!"](images/Anaconda_Shell_Window_Firing_Up_JupyterLab.png)

You will see a web browser tab opening (it may ask you for a specific browser, such as Edge, Chrome, Firefox, Mosaic...).  You'll have a web page called "localhost:8080" open up.  This is the pretend web service housing your Jupyter workspace for coding in Python. 

!["The Jupyter Interface"](images/Jupyter_Hub_Web_Interface.png)

To the left, you will see what looks like a File Manager. (That's your Jupyter File Manager.)  To the right will be a workspace.  It will most likely have a "launcher" pave with apps to push or the last Juptyer Notebook you had open.  You'll also see a menu at the top and other toys around the webpage's perimeter.

### 6.2 A Place For Your ~Crap~ Stuff

Jupyter's framework is expecting your work area to hang off of your home Windows directory. Therefore, I recommend creating a good working directory for your Python development wherever you keep your class materials in your Documents, Dropbox, One-Drive-SDSMT, Google Drive, or other drive access by mouse-clicking on the Jupyter File Manager Sub-Window from your home directory.  

And with that, congratulations!  You have a flexible work environment that allows you to code in Python (and other languages) and create a document that includes traditional word-processing text, pictures, tables, active code, output, graphs, tables, and other resources. This will allow you to create a truly replicable and shareable piece of work that you can share with colleagues or clients. 

### 7 Ways Forward

From here, I have a fast "spinup" course that introduces you to the basic Markdown language to document Python and some basics skills.  Much of it is for students who join my workgroup who have not had Python or need some practice to refresh their skills.  There is also a page of "Stupid Python Tricks" for more advanced use.

Play Rough. Have Fun.
