### The Titanic competition on kaggle
 
The challenge is decribed in: https://www.kaggle.com/c/titanic.

Data samples are available on the competition web page.
### Package overview

There are several notebooks provided: 
  * [EDA + feature extraction](EDA_feature_extraction.ipynb) (used to create derived datasets)
  * [detailed comparison of LightGBM vs XGBoost with different preprocessing](Model_Comparison.ipynb) 
    (an extensive performance comparison using train/valid split as well as cross validation 
    with various models and feature transformers)
  * [basic comparison of LightGBM vs XGBoost](Kernel_Basic_LGB_XGB.ipynb) (a bsaic comparison of different models. 
  This is also available as a kaggle kernel: https://www.kaggle.com/mlisovyi/lightgbm-vs-xgboost-sklearn-api)
  * [Hyper-parameter optimisation of XGBoost and LightGBM models](GBT_LightGBM_XGBoost.ipynb)
  * [Example of linear model based on text features using Vowpal Wabbit](VW_basic_text.ipynb) (This is also available as a kaggle kernel: https://www.kaggle.com/mlisovyi/vowpal-wabbit-decides-who-lives-and-who-dies)
  * [Submission preparation](Prepare_Submission.ipynb)
  
If notebooks are not rendered, when you open then from github in your browser, you can view them using https://nbviewer.jupyter.org/

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
In practice, on a Linux system  with conda installed you will need to:
   * use a conda environment **with python3.5 or python3.6**;
   * `conda install -c anaconda boost` this is important, as it installs a series of boost packages, 
     that are compatible with your conda environment (i.e. python version);
   * `pip install vowpalwabbit` intall the python binding + the cython library of the VW itself.
   This procedure has been tested on Ubuntu 16.04 and 18.04 with a python3.5 and python3.6 environments in conda and geting VW from github.
