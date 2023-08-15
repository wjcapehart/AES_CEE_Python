# Getting the Stuff to Get Started

## 1 Installing Miniconda

I am recommending that you use Miniconda for this.  Minoconda is a "slimmed down" version of the larger Anaconda package that many people recommend.  My experience is that the overhead for Anaconda makes for lots of problems later. The instructions to get Miniconda installed on Windows or MacOS is here:     

*  [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html).

## 2 Adding and Locking-down Conda-Forge as your designated channel

Also I am recommending that you work mostly through the conda-forge community.  Again, this provides a little more consistency in a lot of the packages with which you'll be working. There are scores of repository areas (or "channels" in the conda community) and consequently it is easy to accidentally get a package that was written by Frank that relies on a package written by Susan, which (naturally) is reliant on one developed by Pat.  The result can be a web of dependancies that may eventually come into conflict once you install "that one package."  Therefore we will stick with conda-forge as the "go-to" channel through which to get your packages.  From my experience it's provided the least amount of misery.  

To enable conda-forge, you should open a terminal window (in Unix or Mac it's just a terminal window) and in Windows you can find a Conda Powershell that will drop you into a conda-friendly operating system environment.
Once you have an open working terminal, enter the following commands one line at a time.

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Then run an update to set this channel's packages as *your* packages.

```warning
The late August 2023 installation of Miniconda gave me some rather odd errors when installing. I have revised the script below to reflect that.  Also this semester's install seems to be taking much longer on my Windows machine than in the past.
```

```
conda update --all
conda update -c conda-forge conda
```

## 3 Loading some Libraries.

### 3.1 Commonly-Used Libraries

I recommend that, at this point, you load a number of libraries and packages.

First you will need the Jupyter Resource packages to get the juphter notebooks running

* [Jupyter Notebooks, and JupyterLab](https://jupyter.org) and [IPython](https://ipython.org) environments
  * These are the jupyter, jupyterlab, and notebook packages.  This will also include the IPython interactive python environment
  * [nbopen](https://github.com/takluyver/nbopen) If you want to open a Jupyter Notebook from inside a file manager window for Windows or Mac.

Then you can install (or reinstall) the following basic "must-have" packages for working in data science

* [NumPy](https://numpy.org) The go-to package for basic math, array and matrix handling with Python
* [Matplotlib](https://matplotlib.org) The go-to package for graphics and plotting in Python
* [SciPy](https://www.scipy.org) A library used for scientific computing and technical computing
* [Pandas](https://pandas.pydata.org) A package commonly used for working with tabular data as well as time series data
* [SymPy](https://www.sympy.org/en/index.html) An symbolic algebraic solver engine for Python
* [Scikit-Learn](https://scikit-learn.org/stable/) An open-source set of libraries for regressions, cluster analyses, and similar "machine-learning" activities.
* [seaborn](https://seaborn.pydata.org) An extension to Matplotlib for graph customization and more fancy graphics (often tied to statistical-type graphs.
* [openpyxl](https://openpyxl.readthedocs.io/en/stable/) A Python library to read/write Excel 2010 xlsx/xlsm files
* [pyreadr](https://github.com/ofajardo/pyreadr#pyreadr) A Package to read and write R RData and Rds files into/from pandas dataframes

In your terminal window enter the following *one line at a time*:

```
conda install -c conda-forge jupyterlab  
conda install -c conda-forge numpy matplotlib scipy sympy pandas xarray
conda install -c conda-forge scikit-learn seaborn openpyxl pyreadr
```

```warning
When installing with conda it will first try to reconcile all the packages so any given package doesn't have components that may "break" other packages.  This you may get a warning saying that the "solving environment" has failed and it's trying another set of requirements.

You may also experience a few iterations of "Solving Environment," as shown below.

![Conda Struggling to Reconcile Packages]()


```



### 3.2 More specialized libraries (not needed for CEE 284 students but students wanting to work in Atmospheric Sciences will want some of these)
If you are working in any of the weather & climate groups you will also want to install the following.

* Get the following mapping libraries
  * [Cartopy](https://scitools.org.uk/cartopy/docs/latest/) A basic geospatial processing library which will be essential for mapping
  * [Shapely](https://shapely.readthedocs.io/en/latest/) A support package to help manipulate geometric objects
  * [OWSLib](https://geopython.github.io/OWSLib) Access to the Open Geoscience Consortium resources and services.  Lots of good mapping goodies to have.
  * [pyProj](https://pyproj4.github.io/pyproj/stable/) An interface for working with map projections
  * [geopandas](https://geopandas.org/en/stable/) Geospatial access that leverages Pandas's Dataframe style resoruces

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
  * [cf-plot](http://ajheaps.github.io/cf-plot) a set of Python routines for making the common contour, vector and line plots that climate researchers use
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
WRF-Python and Basemap for Apple Silicon machines have been temporarily removed from conda-forge so proceed with caution.
```

```
conda install -c conda-forge wrf-python 
conda install -c conda-forge basemap 
```

## 4 Get Git (If you don't already have it).

Git is a revision-control program and environment that accesses code repositories made public to the larger user community.  To use some resources, it's not a bad idea to have.  If you have a Mac, you already have it.  If you are on Windows, you can get it from your terminal window by typing the following command.

```
conda install -c conda-forge git
```

## 5 Adding a library that we'll be using: "version_information"

Conda and Conda-Forge have a large number of libraries that we'll be using.  But we will be needing one more that doesn't always come in with the default distribution of Python.  *"Version_Information"* is a tool to extract information on the modules, operating system and other resources used in any Juptyer Notebook Python session.  Currently, the Version_Information is not compatible with the current release of Python and Robert Johansson, the original author of the package no longer supports it but since it has a cult following (including me!), some of us have been trying to maintain it.

You can access it using the terminal window:

```
pip install git+https://github.com/wjcapehart/version_information
```


## 6 A Place For Your Stuff

Jupyter's framework is expecting your work area to hang off of your home Windows directory. Therefore, rather than a network drive like your H: drive, you probably should make a working directory in your Documents, Dropbox, One-Drive, Google Drive or other drive access by mouse-clicking on your file manager from your home directory.  

```
jupyterlab
```
