# New poetry project

# part 1

`poetry new pyclick`{{execute}}

`cd pyclick`{{execute}}

`tree`{{execute}}

`poetry install`{{execute}}

`poetry add pendulum coo`{{execute}}

`poetry add -D flake8 mypy`{{execute}}

`poetry add -D black --allow-prereleases`{{execute}}

# is no longer in prerelease

`poetry remove coo`{{execute}}

`poetry remove -D mypy`{{execute}}

# Starting an virtual envirnoment

`poetry shell`

`exit`

# Two ways to start python

`poetry run  python`

`poetry shell`   
`python`

```
poetry new [package-name]	Start a new Python Project.
poetry init	Create a pyproject.toml file interactively.
poetry install	Install the packages inside the pyproject.toml file.
poetry add [package-name]	Add a package to a Virtual Environment.
poetry add -D [package-name]	Add a dev package to a Virtual Environment.
poetry remove [package-name]	Remove a package from a Virtual Environment.
poetry remove -D [package-name]	Remove a dev package from a Virtual Environment.
poetry self:update
```

# part 2

https://www.pythoncheatsheet.org/blog/python-projects-with-poetry-and-vscode-part-2/

`poetry update`{{execute}}

IN VSC

poetry shell   
code .