# Getting Started: Environments

Your Jupyter workspace has a set of pre-installed libraries, depending on which server you chose when starting up this JupyterLab. Currently you can choose between the: 

* **Minimal environment**: just Python and a minimal amount of pre-installed libraries
* **Datascience environment**: offering Python, R, and Julia
* **EarthCARE environment**: the base environments includes the EarthCARE data plotting library 

<span style="color:red"><strong>Note:</strong></span> If you would like to switch servers, you can navigate to the top bar: File > Hub Control Panel > Stop My Server.
If you need libraries that are not pre-installed, we suggest using an environment manager; for this you can use virtual environments and `conda` is pre-installed to help with this. 

## Creating and managing environments 

`venv` Creating Python's Built-In Virtual Environment 
```bash
python -m venv /home/jovyan/my_env
source /home/jovyan/my_env/bin/activate
#optional 
pip install package_name 
```

---

`conda` Environment and Package Manager 

<span style="color:green"><strong>Tip:</strong></span> When working with Conda, managing your environments effectively is key to maintaining clean and organized projects. One common practice is to set up a dedicated `envs` folder within your project directory to store your environments locally.

Creating a conda environment: 


```bash
conda create -p ./envs/my_env
source /home/jovyan/envs/my_env/bin/activate
#optional 
conda install package_name 
```

<span style="color:red"><strong>Warning:</strong></span> Only environments that are saved and contained within a folder are persistent. 

You can manage conda environments with the following commands:
  ```bash
  conda env list
  conda env remove -p environment_path
  ```

## Setting up an environment as a kernel 

1. Activate the environmet you want to use as a kernel
2. Install ipykernel ```conda install ipykernel```
3. Run ```python -m ipykernel install --user --name my_env --display-name "my_kernel"```

You can manage Jupyter kernels with the following commands:
  ```bash
  jupyter kernelspec list # lists available kernels
  jupyter kernelspec uninstall my_env # delete an existing kernel 
```


## Installing packages 
When working in Python, especially with Jupyter Notebooks and virtual environments or conda environments, it's important to understand the difference between installing packages via the **terminal** and from **within a notebook**. 

You can install packages using tools like `pip` or `conda` directly from your system's terminal, **after ensuring you have activated the environment**:

```bash
pip install numpy
# or
conda install numpy
```

Or you can install packages inside a cell from **within a Jupyter Notebook** using the magic command built into IPython/Jupyter. This ensure that the package is installed into the active kernel's environment. 

```python
%pip install numpy     
# or
%conda install numpy
```
<span style="color:red"><strong>Warning:</strong></span> Avoid using `!pip install numpy` inside a notebook cell. This installs the package into your system's base environment, **not the environment linked to your Jupyter kernel**, causing confusion when the package appears "missing" in the notebook.
