![GitHub](https://img.shields.io/github/license/ennanco/MIA_ML1?style=flat-square) ![Python](https://img.shields.io/badge/Python-3.10-blue?logo=Python)

![Banner](img/MLII.png)

This repository contains set of tutorial which are the introduction for the topics covered in the subject Machine Learning II of the Master in Artificial Intelligence tought at the three universities of Galicia, i. e., University of A Coruña (UDC), University of Santiago de Compostela (USC), University of Vigo (UVigo).

# Teaching Staff:
* David Mera Pérez (coordinator, USC)
* Enrique Fernández Blanco (UDC)
* David Olivieri Cecchi (UVigo)


# Development Environment

The practices will be developed via Notebooks. In order to run them you will need to install Python (>3.8), a Notebook server (e.g. Jupyter) and all the necessary packages for executing the programs. There are different possible configurations, you can use the configuration more appropriate for your interest. However, in this manual we will give you some alternatives:


1. [Google Colab](https://colab.research.google.com/) environment to run the Notebooks. Colab allows you to load Notebooks and also create new ones. It is also possible to install new libraries using commands such as <code>!pip install xxx</code>. The free account has some limitations, most of them linked to the computing resources.

2. [Python](https://www.python.org/downloads/) (>3.8) and [pip](https://pip.pypa.io/en/stable/installation/) (pip is automatically installed if you are working with virtual environments or if you are installed Python from the official web page). Once Python is installed, Jupyter and the rest of the necessary packages can be installed using <code>pip install xxx</code>.

3. [Anaconda](https://www.anaconda.com/) is a development framework focused on Data Science and Machine Learning, which is available in Windows, Linux and MacOS. This framework is composed of different packages and software including Jupyter and [conda](https://docs.conda.io/en/latest/). The latter is a package environment management  system that allows us to have different virtual package environments in the same system. While `pip` installs packages at system level and may cause conflicts, conda allows to have each package configuration in a separate virtual environment without conflicts.  All the dependencies are managed by conda. Users can activate and deactivate virtual environments at their discretion. The way to manage the packages is using the command <code>conda install xxx</code> instead of pip.

4. [Miniconda](https://docs.conda.io/en/latest/miniconda.html) is a free minimal installer for conda,  which is available in Windows, Linux and MacOS. It is a small, bootstrap version of Anaconda that includes *only* conda, Python, the packages they depend on, and a small number of other useful packages.
Anaconda is a huge framework with many unnecessary packages. Miniconda allows the user only install the necesary ones.  It must be noted that Jupyter is not included in Minicoda. It must be installed as a new package  <code>conda install jupyter</code>.




## Conda Environments

**Conda commands for managing environments**

[https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html](
https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

**Conda cheatsheet**

[https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf](
https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf)


### Useful conda commands

**All these commands must be run in a terminal**. These commands have been checked in a Linux system. Some differences may appear in other distributions.


**Create an environment**

<code> conda create --name environment_name</code>

It is possible to establish a specific Python version for the environment.

<code> conda create --name environment_name python=x.y.z</code>

**Activate the environment**

The activation of the environment allows us to work with the packages and features of that environment. It is important to keep in mind that outside the environment these libraries do not necessarily exist.

<code>conda activate  environment_name</code>

**Deactivate an environment**

This command allows us to exit the environment.

<code>conda deactivate</code>

**Remove an environment**

This operation cannot be reversed.

<code>conda remove  --name environment_name -all</code>

**List all the available environments in our system**

<code>conda info --envs</code>

Alternative option to list all the available environments:

<code>conda envs list</code>

**Install a new package in the environment**

To install a package in an environment, the environment must be active (<code>conda activate  environment_name</code>).

<code>conda install package_name</code>

**List all the installed packages in a environment**

The environment must be active to list all its packages (<code> conda activate  environment_name</code>).

<code>conda list</code>

**Export an environment file**

<code>conda env export > environment_file_name.yml</code>

**Export an environment file across platforms**

<code>conda env export --from-history > environment_file_name.yml</code>

**Create a new environment from a .yml file**

<code>conda env create -f environment_file_name.yml</code>

## Create the conda environment for developing the practices

<code>conda create --name ml2</code>

*Make sure to note the installation directory of the virtual environment if you intend to use 'pip' from within it*

**Packages linked to the Online learning practices with River**

<code>conda install jupyter scikit-learn pandas matplotlib python-graphviz rich</code>



*Note: The package installation from conda-forge use to be slow.*

**Important!** There are two alternatives at this point (we recommend to use the second option):
1. To acquire the River package from a conda repository, install it from the conda-forge. However, it's important to note that the latest available version of River in conda-forge is 0.13.

<code>conda install -c conda-forge river </code>


2. To acquire the most recent version of the River package (0.22.0), install it using pip within your virtual environment. Ensure that you utilize the pip version located specifically within your virtual environment, not the global one. Locate your virtual environment directory, typically found at a path similar to /anaconda/envs/virtual_env_name/, whether you installed Anaconda.

<code>/home/user/anaconda/envs/virtual_env_name/bin/pip install river</code>

*Note*: To locale your virtual environment storage you can execute the following commands:
<code>
conda activate virtual_env_name \
echo $CONDA_PREFIX
</code>


**Packages linked to the Federated Learning practices with Flower**

There is a FLower package avaible in the conda-forge repository:

<code>conda install -c conda-forge flwr</code>

**However**, the official web page recommends to install it from the pip repository in order to get the newest and stablest version. **Note** that you should use the pip version located specifically within your virtual environment.

<code>pip install flwr</code>

*Note*: To locale your virtual environment storage you can execute the following commands:
<code>
conda activate virtual_env_name \
echo $CONDA_PREFIX
</code>

For simulations that use the Virtual Client Engine, flwr should be installed with the simulation extra:

<code>pip install flwr[simulation]</code> ***This is our scenario**

It's important to note that Flower is not a learning framework in itself, and as such, it wraps other machine learning frameworks like TensorFlow, PyTorch, or Scikit-learn in the communication layer to enable federated learning.

In the laboratory practices of this subject we are going to use tensorflow


<code>conda install tensorflow</code>

Also, it is worth mentioning that since version 1.15 the simulation mode has a dependency on the ray library to spread the calculations. Therefore, the following line would be required:

<code>pip install ray[default]</code>

**Note** that you should use the pip version located specifically within your virtual environment.

## Notebooks
To obtain the notebooks for developing laboratory practices, you can either download the ZIP file from GitHub or clone the repository using Git via HTTPS or SSH. Please note that for the SSH connection, you must have an SSH certificate.

<code>git clone git@github.com:ennanco/MIA_ML2.git</code>

**Important**: The examples located within the initial three working units (online ML+Concept Drift) have been specifically tailored for compatibility with **River 0.22**.


## Jupyter

In order to run Jupyter, the following command must be executed (the appropriate conda environment must be activated if necessary).

<code>jupyter notebook</code>

Once executed it is necessary to open the browser and access to  http://localhost:8888/.

The security token can be found in the terminal where we execute the command.


# Troubleshooting
- River's wrapper module, designed for integration with libraries like scikit-learn, is currently experiencing compatibility issues.  Scikit-Learn version 1.6.1 (released January 2025) exhibits integration problems with River 0.22, resulting in an <code>'super' object has no attribute '__sklearn_tags__' </code> error in Unit02.  Until River is updated, downgrading scikit-learn is the recommended workaround.

<code>conda uninstall scikit-learn</code>

<code>conda install scikit-learn=1.5.2 </code>



