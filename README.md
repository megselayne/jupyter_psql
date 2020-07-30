# jupyter_psql
Using jupyter for PSQL
# How to use Jupyter with postgresql
- install Jupyter notebook or Jupyter lab
	- Jupyter notebook has some extra features, but is still in beta, though quite widely used in the Data Science community. FYI, notebook doesn’t have dark mode
	- [Installation — JupyterLab 2.2.2 documentation](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html)
- install python-sql
	- `pip install ipython-sql`
- launch jupyter-lab
	- type `jupyter-lab` from the folder you want to work in Jupyter. This only matters if you want access to files
	- this terminal is now exclusively running your Jupiter lab kernel (like psql does) if you need to navigate your directory etc, open a new terminal and leave this one alone.
	- to shutdown the kernel at any time: `control+c`, confirm `y`
- starter code to get you up and running
- run  `%load_ext sql`  in your first cell
	- loads python-sql which you installed
- run `%sql postgresql://localhost/databaseName` in the next cell
- That’s it! To tell Jupyter that you’re running SQL, start each cell with :
	- `%%sql` and then on the next lines, type your SQL!


## Executing cells
- to run your SQL in a given cell, hit `shift+return`
- semi colons are not necessary at the end of your statements in Jupyter, but they won’t break anything if you include it

## Variations on Selecting Tables and Databases
- outside the terminal, you can’t use backslash commands to navigate the database or tables ie `\l`, `\d` etc
- Instead, you’ll need to use sql queries for this information. 
- Here are some common queriers you may need
- Schema for table:
```
%%sql
SELECT
   table_name, 
   column_name, 
   data_type 
FROM
   information_schema.columns
WHERE
   table_name = 'table_name';
```

- What tables are in your connected database:
```
%%sql
SELECT *
FROM pg_catalog.pg_tables
WHERE schemaname = 'public'
```

