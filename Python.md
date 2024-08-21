Python
--------------------

### Amend txt and list:

https://pythonprinciples.com/blog/lists-of-strings-in-python/

### Create a virtual enviroment in a specific path #the name if the virtual enviroment)

```bash 
python -m venv /path/to/new/virtual/environment
```

### Check the consol path of python 

```bash
which python
```

### upgrade pip 

```bash
python -m pip install --upgrade pip
```

Or 

```bash 
pip install --upgrade pip 
```

### install requirments from requirment.txt
Make sure you are in the directory of where the requirements.txt is stored and that your bash consol is running within the correct python virtual enviroment to avoid installing requirments in the global python. 

```bash
python -m pip install -r requirements.txt
```
Or 

```bash
pip install -r requirements.txt

## Refrences: 
[reference1: python venv documentation](https://docs.python.org/3/library/venv.html)
