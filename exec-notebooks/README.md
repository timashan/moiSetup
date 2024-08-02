# Execute Notebboks Programmatically

[nbconvert docs](https://nbconvert.readthedocs.io/en/latest/execute_api.html)

## Install

```bash
pip install nbformat nbconvert
```

## Run

```py
import nbformat
from nbconvert.preprocessors import ExecutePreprocessor

with open(notebook_filename) as f:
    nb = nbformat.read(f, as_version=4)

ep = ExecutePreprocessor(timeout=600, kernel_name='python3')
ep.preprocess(nb, {'metadata': {'path': 'notebooks/'}})
```
