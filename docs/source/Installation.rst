.. ADEPT documentation master file, created by
   sphinx-quickstart on Thu Sep 16 19:43:51 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Installation
============

The ADEPT package is developed based on the pytorch and DGL framework and can be implemented on both GPU and CPU. 
We recommend running the package on GPU. Please ensure that pytorch and cudnn are installed correctly. 
To run MaskGraphene, all dependencies included in the file 'requirement.txt' need to be installed. We highly recommend to install MaskGraphene with `Anaconda <https://docs.anaconda.com/free/anaconda/install/index.html>`_.


Anaconda
------------
For convenience, we suggest using a separate conda environment for running MaskGraphene. Please ensure anaconda3 is installed.

Create conda environment and install MaskGraphene package.

.. code-block:: python

   #create an environment called MG
   conda create -n MG python=3.9
   
   #activate your environment
   conda activate MG

   #pull source code from the repo
   git clone https://github.com/OliiverHu/MaskGraphene.git
   
   #install package
   
   pip install -r requirements.txt
   
   #To use the environment in jupyter notebook, add python kernel for this environment.

   pip install ipykernel

   python -m ipykernel install --user --name=MG
   
   #For DGL package, please refer to https://www.dgl.ai/pages/start.html

   pip install  dgl -f https://data.dgl.ai/wheels/cu117/repo.html

   pip install  dglgo -f https://data.dgl.ai/wheels-test/repo.html

This serves as an example for installing MG with certain cuda version. However, one might need to adapt to a proper version combination of these packages to make the env runnable.