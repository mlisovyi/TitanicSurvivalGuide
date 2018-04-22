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

The notebooks are developed in python3.6, but will most likely work in any python3 environment. 
All of those can be installed with conda (either mini- or ana-).
Just do something like
```bash
conda install numpy pandas matplotlib seaborn scikit-learn ipykernel jupyther xgboost lightgbm
```
You might need to add conda-forge to the list of channels: `conda config --add channels conda-forge`,
if you have not done so yet (the installation would fail complaining that a subset of modules can not be found).


