.. ADEPT documentation master file, created by
   sphinx-quickstart on Thu Sep 16 19:43:51 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Installation
============

The ADEPT package is developed based on the pytorch and pytorch-geometric framework and can be implemented on both GPU and CPU. 
We recommend running the package on GPU. Please ensure that pytorch and cudnn are installed correctly. 
To run ADEPT, all dependencies included in the file 'requirement.txt' need to be installed. We highly recommend to install ADEPT with `Anaconda <https://docs.anaconda.com/free/anaconda/install/index.html>`_.


Anaconda
------------
For convenience, we suggest using a separate conda environment for running ADEPT. Please ensure anaconda3 is installed.

Create conda environment and install MaskGraphene package.

.. code-block:: python

   ### Installation from github
   1. git clone --recursive https://github.com/maiziezhoulab/AquilaDeepFilter.git

   2. conda create -n [EnvName] python=3.7

   3. source activate [EnvName]

   4. install pytorch (https://pytorch.org/get-started/locally/) + pytorch-geometric (https://pytorch-geometric.readthedocs.io/en/latest/install/installation.html) before everything

   5. pip install -r requirements.txt

   6. pip install scanpy python-igraph rpy2

   7. install.packages("mclust") with R

Google Colab
------------

Colab user can link to google drive and enter the folder through code below：

.. code-block:: python
   


   from google.colab import drive
   drive.mount('/content/drive')

   # Modify it to the name you saved for the fold with
   folder_name = 'ADEPT/'
   import sys
   sys.path.append('/content/drive/My Drive/{}'.format(folder_name))

   %cd /content/drive/My\ Drive/$folder_name


In colab environment (with complete base env), you need to install libraries below:

.. code-block:: python
   !pip install torch-geometric
   !pip install -r requirements.txt
   !pip install scanpy
   !pip install python-igraph
   !pip install rpy2

   import torch
   !pip install torch-scatter torch-sparse -f https://data.pyg.org/whl/torch-{torch.__version__}.html

   import rpy2.robjects as robjects

   install_cmd = "install.packages('mclust', repos='http://cran.r-project.org')"
   robjects.r(install_cmd)

For possible error, please try:

.. code-block:: python
   """
      OSError: cannot load library 'C:\Program Files\R\R-4.3.1\bin\x64\R.dll':error 0x780
   """
   import os
   os.environ['R_HOME'] = 'C:\\Program Files\\R\\R-4.3.1\\' # replace it with your own path

This serves as an example for installing ADEPT with certain cuda version. However, one might need to adapt to a proper version combination of these packages to make the env runnable.