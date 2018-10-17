### The Titanic competition on kaggle
 
The challenge is decribed in: https://www.kaggle.com/c/titanic.

Data samples are available on the competition web page.
### Package overview

There are several notebooks provided: 
  * [EDA + feature extraction](EDA_feature_extraction.ipynb) (used to create derived datasets)
  * [comparison of performance for different models](Model_Comparison.ipynb) 
    (for a simple comparison using train/valid split or sross validation with a pipe of feature transformers)
  * more to come...

### Environment setup

The notebooks are developed in python3.5, but most of the code will most likely work in any python3 environment. 
All of those can be installed with conda (either mini- or ana-).
Just do something like
```bash
conda install numpy pandas matplotlib seaborn scikit-learn ipykernel jupyter xgboost lightgbm
```
You might need to add conda-forge to the list of channels: `conda config --add channels conda-forge`,
if you have not done so yet (the installation would fail complaining that a subset of modules can not be found).

#### Environment setup for Vowpal Wabbit (VW)
If you want to try the Vowpal Wabbit (https://github.com/JohnLangford/vowpal_wabbit) for classification,
you will need to play additional tricks: read and follow the instructions on their 
[README of the python package](https://github.com/JohnLangford/vowpal_wabbit/blob/master/python/README.rst).
In practice, on a Linux system you will need to:
   * use a conda environment **with python3.5**. 
     I did not manage to make it work in python3.6;
   * `apt-get install libboost-program-options-dev zlib1g-dev libboost-python-dev` 
     I'm not sure how relevant this is, though;
   * `conda install -c anaconda boost` this is important, as it installs a series of boost packages, 
     that are compatible with your conda environment (i.e. python version);
   * `pip install vowpalwabbit` intall the python binding + the cython library of the VW itself.
   This procedure has been tested on Ubuntu 16.04 with a python3.5 environment in anaconda2 and geting VW 8.5.0 from pypi
