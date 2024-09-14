# How to clear notebook metadata

Add this to your local `.git/config` or global `~/.gitconfig:`\
From [stackoverflow](https://stackoverflow.com/questions/28908319/how-to-clear-jupyter-notebooks-output-in-all-cells-from-the-linux-terminal/58004619#58004619)

## Clear Output

```bash
pip install nbconvert
```

```bash
[filter "strip-notebook-output"]
    clean = "jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR"
```

## Clear execution_count

[jq docs](https://jqlang.github.io/jq/download/)

```bash
scoop install jq
```

```bash
[filter "nbstrip"]
    clean = jq --indent 1 '(.. |."execution_count"? | select(. != null)) = null'
    smudge = cat
```

## Edit global config with

From [stackoverflow](https://stackoverflow.com/questions/66476216/how-can-i-edit-the-git-config-file-from-the-git-terminal)

```bash
git config --global --edit
```

Add this `.gitattributes` to project with notebooks & replace with desired `<filter>`

```bash
*.ipynb filter=<filter>
```
