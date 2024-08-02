# How to clear notebook metadata

Add this to your local `.git/config` or global `~/.gitconfig:`\
From [stackoverflow](https://stackoverflow.com/questions/28908319/how-to-clear-jupyter-notebooks-output-in-all-cells-from-the-linux-terminal/58004619#58004619)

```bash
[filter "strip-notebook-output"]
    clean = "jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR"
```

Edit global config with\
From [stackoverflow](https://stackoverflow.com/questions/66476216/how-can-i-edit-the-git-config-file-from-the-git-terminal)

```bash
git config --global --edit
```

Add this `.gitattributes` to project with notebooks.

```bash
*.ipynb filter=strip-notebook-output
```
