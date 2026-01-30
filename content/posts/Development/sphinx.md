---
title: "Sphinx"
description: "Minimal notes for installing and bootstrapping Sphinx documentation"
tags: ["development"]
draft: false
---


The official [Github](https://github.com/sphinx-doc/sphinx) page of Sphinx, Sphinx [Themes](https://sphinx-themes.org/) and Sphinx [Docs](https://www.sphinx-doc.org/en/master/index.html)

```bash
uv pip install sphinx
```

Verify installation using,

```bash
sphinx-build --version
```

To create documentation layout,

```bash
sphinx-quickstart docs
```

**Docs folder should be there**

```bash
ls
```

It should show the `docs` folder inside the directory

**To build**

```bash
sphinx-build -M html docs/source/ docs/build/
```

I have moved the `docs` inside `sphinx` because github can either deploy from `root` or `/docs`. I created a `docs` folder in main dir and copied the contents of `docs/build/html` to `docs`. We also need to add `.nojekyll` file inside `docs` so that the static files are served. Since I have written down all the docs in wiki as `markdown`, it is better to include a plugin that reads `.md` files. So install, `myst_parser`.

Add the plugin to the `conf.py` file

```python
extensions = ["myst_parser",]

source_suffix = {
    ".rst": "restructuredtext",
    ".md": "markdown",
}
```

In `index.rst`, include the code to read the pages,

```bash
.. toctree::
   :maxdepth: 2
   :caption: Contents:
   :glob:

   pages/*
```

Create a folder called `pages` inside `sources` and copy paste all the `.md` files from `wiki`. Now run sphinx and copy all the files inside `build` to `docs` in the main dir. Add `.nojekyll` file inside `docs/` so that the static files are rendered.
