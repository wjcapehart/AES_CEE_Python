# Getting the Stuff to Get Started

## 1 Installing Miniconda

I am recommending that you use Miniconda for this.  Minoconda is a "slimmed down" version of the larger Anaconda package that many people recommend.  My experience is that the overhead for Anaconda makes for lots of problems later. The instructions to get Miniconda installed on Windows or MacOS is here:     

*  [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html).

## 2 Adding and Locking-down Conda-Forge as your designated channel

Also I am recommending that you work mostly through the conda-forge community.  Again, this provides a little more consistency in a lot of the packages with which you'll be working. There are scores of repository areas (or "channels" in the conda community) and consequently it is easy to accidentally get a package that was written by Frank that relies on a package written by Susan, which (naturally) is reliant on one developed by Pat.  The result can be a web of dependancies that may eventually come into conflict once you install "that one package."  Therefore we will stick with conda-forge as the "go-to" channel through which to get your packages.  From my experience it's provided the least amount of misery.  

To enable conda-forge, you should open a terminal window (in Unix or Mac it's just a terminal window) and in Windows you can find a Conda Powershell that will drop you into a conda-friendly operating system environment.
Once you have an open working terminal enter the following commands one line at a time.

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Then run an update to set this channels packages as *your* packages.

```
conda update --all
```

## 3 Get Git (If you don't already have it).

Git is a revision-control program and environment that accesses code repositories that are made public to the larger user community.  To use some resources it's not a bad idea to have.  If you have a Mac, you already have it.  If you are on Windows you can get it from your terminal window by typing the following command

```
conda install -c conda-forge git
```
## 4 Loading some popular libraries.

I'm going to recommend that at this point you load a number of libraries and packages.

First you will need the Jupyter Resource packages to get the juphter notebooks running

* [Jupyter Notebooks, and JupyterLab](https://jupyter.org) and [IPython](https://ipython.org) environments
  * These are the jupyter, jupyterlab, and notebook packages.  This will also include the IPython interactive python environment
  * [nbopen](https://github.com/takluyver/nbopen) If you want to open a Jupyter Notebook from inside a file manager window for Windows or Mac. (Follow the directions at this link [here]().)

Then you can install (or reinstall) the following basic "must-have" packages for working in data science

* [NumPy](https://numpy.org) The go-to package for basic math, array and matrix handling with Python
* [Matplotlib](https://matplotlib.org) The go-to package for graphics and plotting in Python
* [SciPy](https://www.scipy.org) A library used for scientific computing and technical computing
* [Pandas](https://pandas.pydata.org) A package commonly used for working with tabular data as well as time series data
* [SymPy](https://www.sympy.org/en/index.html) An symbolic algebraic solver engine for Python
* [Scikit-Learn](https://scikit-learn.org/stable/) An open-source set of libraries for regressions, cluster analyses, and similar "machine-learning" activities.
* [seaborn](https://seaborn.pydata.org) An extension to Matplotlib for graph customization and more fancy graphics (often tied to statistical-type graphs.

In your terminal window enter the following:

```
conda install -c conda-forge jupyter jupyterlab notebook urllib3 nbopen
conda install -c conda-forge numpy matplotlib scipy sympy pandas  scikit-learn seaborn

```
If you are working in any of the weather and climate groups you will also want to install the following.

* Get the following mapping libraries
  * [Cartopy](https://scitools.org.uk/cartopy/docs/latest/) A basic geospatial processing library which will be essential for mapping
  * [Shapely](https://shapely.readthedocs.io/en/latest/) A support package to help manipulate geometric objects
  * [OWSLib](https://geopython.github.io/OWSLib) Access to the Open Geoscience Consortium resources and services.  Lots of good mapping goodies to have.
  * [pyProj](https://pyproj4.github.io/pyproj/stable/) An interface for working with map projections

* Get the following complex data and meteo data resources
  * [xarray](http://xarray.pydata.org/en/stable/) Data manipulation and archiving of multi-dimensional datasets
  * [metpy](https://unidata.github.io/MetPy/latest/index.html) UCAR-Unidata tools for reading, viewing, and analyzing meteo data
  * [Siphon](https://unidata.github.io/siphon/latest/) UCAR-Unidata support for accessing remote meteo data
  * [netCDF4](https://unidata.github.io/netcdf4-python/) UCAR-Unidata tools for NetCDF4 Support
  * [cfGrib](https://github.com/ecmwf/cfgrib) ECMWF tools for WMO Gridded Binary (GRIB 1/2) support
  * [pyGrib](https://jswhit.github.io/pygrib/)  NOAA-ESRL tools for WMO Gridded Binary (GRIB 1/2) support
  * [cftime](https://unidata.github.io/cftime/) UCAR-Unidata support for time data support (including 360-day, leap-year-free 365-day, and other quirky calendars, that only a meteorologist would love because the rest of the world are monsters)

```
conda install -c conda-forge shapely cartopy OWSLib pyproj
conda install -c conda-forge xarray metpy netCDF4 siphon cfgrib pygrib cftime cf-python
conda install -c conda-forge  wrf-python usgs
```

## 5 Adding a library that we'll be using: "version_information"

Conda and Conda-Forge has a large number of libaries that we'll be using.  But we will be needing one more that doesn't always come in with the default distribution of Python.  *"Version_Information"* is a tool to extract information on the modules, operating system and other resources used in any Juptyer Notebook Python session.  Currently the Version_Information is not compatable with the current release of Python and the Robert Johansson, the original author of the package no longer supports it but since it has cult following (including me!), some of us have been trying to maintain it

You can access it using the terminal window:

```
pip install git+https://github.com/wjcapehart/version_information
```


## 6 Getting LaTeX for Creating Documents for Printing

I am not a fan of the PDF output from Jupyter notebooks, favoring exporting them as HTML files.

BUT... Jupyter uses LaTeX produce PDF files of your notebook. If you *really* want to do that, you will need to install the Windows version of TeX, "MikTeX" available at [https://miktex.org](https://miktex.org)

You have fun.

## 7 A Place For Your Stuff

Jupyter's framework is expecting your work area to hang off of your home windows directory. Therefore, rather then a network drive like your H: drive, you probably should make a work directory in your Documents, Dropbox, One-Drive, Google-Drive or other drive access able by clocking on your file manager from your home directory.  

The exception is you have the [nbopen](https://github.com/takluyver/nbopen) tool that works with the Jupyter Notebook (sorry, it's not ready for JupyterLab, yet).  If you need something in another part of your file system to carry your notebooks, you can use that.   If you are a "power-user" you can do the same thing by using a terminal window and just "cd-ing" yourself into any given directory and just opening the notebook there via the command

```
jupyter notebook
```