# jupyter_psql
Using jupyter for PSQL
# How to use Jupyter with postgresql
- install Jupyter notebook or Jupyter lab
	- JupyterLab has extra features (dark mode etc) and is the newer version of Jupyter Notebook.
	- [Installation — JupyterLab 2.2.2 documentation](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html)
	- If you use pip: `pip install jupyterlab`
- install python-sql
	- `pip install ipython-sql`
- launch jupyter-lab
	- type `jupyter-lab` from the folder you want to work in Jupyter. This only matters if you want access to files
	- this terminal is now exclusively running your Jupyter lab kernel (like psql does) if you need to navigate your directory etc, open a new terminal and leave this one alone.
	- to shutdown the kernel at any time: `control+c`, confirm `y`

## Go to Jupyter Sample Notebook
- Once you've installed the above, go checkout the sample starter notebook for directions on how to use jupyter and get up and running!
