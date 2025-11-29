# lhcb-starterkit-2022

This repository contains a tutorial for the [`zfit`](https://github.com/zfit/zfit) and [`Minuit`](https://iminuit.readthedocs.io/en/stable/) libraries for parameter estimation in python that was created for the LHCb starterkit 2022.

The lesson is divided into three different parts:
 - [Part I - zfit Basics](https://github.com/rvlaak/lhcb-starterkit-2025/blob/main/zfitBasics.ipynb) sets the scene for the lesson and introduces the basics needed to run a fit in `zfit`. The fit result is investigated and different cost functions are introduced.
 - [Part II - zfit Fit Failure](https://github.com/rvlaak/lhcb-starterkit-2025/blob/main/zfitFitFailure.ipynb) tries to give some examples as to why a fit might be unstable or fail and how to avoid them.
 - [Part III - zfit Advanced](https://github.com/rvlaak/lhcb-starterkit-2025/blob/main/zfitAdvanced.ipynb) shows examples on more advanced use cases for `zfit`, like performing pseudoexperiments, statistical background subtraction, simultanous fits, fits to a disjointed observable space and showing pull plots.

## Installation

The notebook was created having `python 3.10` in mind with `zfit` version `0.28.0` and Minuit `2.32.0`.
Additionally required are the dependencies of the packages, such as `tensorflow`, and `numpy`.
The full requirements can be found in [requirements.txt](https://github.com/rvlaak/lhcb-starterkit-2025/blob/main/requirements.txt).
An installation guide can be found on [the zfit webpage](https://zfit.readthedocs.io/en/latest/getting_started/installation.html).

The way I recommend to set up zfit is through a virtual environment for python with [miniconda](https://docs.conda.io/en/latest/miniconda.html).
I use the following commands to install a version of zfit and dependencies needed for these tutorials:
```
conda create -n zfit_env python=3.10 -y
conda activate zfit_env
conda install -c conda-forge zfit -y
conda install -c conda-forge numpy scipy matplotlib pandas ipywidgets hepstats -y
```
Note that at the time of writing, the version of tensorflow that is automatically installed by zfit, might be unstable when paired with zfit's sampler used at some points in this tutorial.
In case of a kernel crash, a quick fix is to downgrade to specific stable versions:
```
pip install tensorflow==2.16.2 tensorflow-probability==0.24.0
```


## Acknowledgements

This repository is largely taken from [the 2022 LHCb Starterkit](https://github.com/schmitse/lhcb-starterkit-2022/tree/main) by Sebastian Schmitt. Many thanks to Sebastian for giving me permission to use his repository for the 2025 Starterkit!

I extend my gratitude to Jonas Eschle and Iason Krommydas for useful discussion in the preparation of this tutorial and their development of [`zfit`](https://github.com/zfit/zfit).

I also want to express gratitude to those mentioned by Sebastian to have helped in the improvement of the presentation of [the original content](https://github.com/schmitse/lhcb-starterkit-2022/tree/main); Lorenzo Paolucci, Gediminas Sarpis, and Dan Thompson. 

Parts of [the original tutorial](https://github.com/schmitse/lhcb-starterkit-2022/tree/main) are inspired by [Hans Dembinskis pyHEP](https://nbviewer.org/github/HDembinski/PyHEP-2022-iminuit/blob/main/iminuit.ipynb) tutorial for `Minuit` and [Statistical Data Analysis](https://books.google.de/books/about/Statistical_Data_Analysis.html?hl=de&id=ff8ZyW0nlJAC&redir_esc=y) by Glen Cowan.