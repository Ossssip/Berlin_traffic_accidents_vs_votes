# BerlinWeather

At this stage this repo is for testing things and figuring out how to work together. 
So far I've tried made sure we can run the notebooks from this repo both locally and with Google Colab

## Colab
Go to https://colab.research.google.com/github/, authorize yourself, tick "include private repos", after that your should see the notebook file(s) in this repo

### Revision history and commiting changes
- Apparently Colab already has built-in revision history tool, it is under File->Revision history
- When some changes to notebook a made (or a new notebook file created), you can commit it to the repo using File->Save a copy in Github

## Running on local PC
I run Jupyter Notebook from Anaconda on a Windows machine, here are the steps I made:
- install git/git gui of your choice, clone the repo
- install anaconda
- from anaconda prompt, create and activate a separate enviroment:
```
conda create --name EnvName
conda activate EnvName
```
- install ipykernel to be able to run notebooks from that enviroment (all other pakages should be installed from the Notebook itself in order to be compatible with Colab):
```
conda install -c anaconda ipykernel
python -m ipykernel install --user --name=EnvName
```
- run Jupyter Notebook, don't forget to choose the right Kernel, that's it!

### Revision history
'git diff' is not very usable for .ipynb files, but one can use [nbdime](https://nbdime.readthedocs.io/en/latest/) for diffing and merging. You can install it from conda prompt:
```
conda install -c conda-forge nbdime
```
set up git integration
```
nbdime config-git --enable --global
```
Afterfords, you can use a web-based GUI to view the notebook diff, for example
```
nbdiff-web 551d6ee 4210941
```
