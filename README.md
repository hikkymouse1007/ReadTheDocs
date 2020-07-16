# ReadTheDocs
https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html

イメージのpull

```
docker pull readthedocs/build:latest
```

コンテナ起動

```
docker run -itd --name myreadthedocs01 readthedocs/build
```

コンテナログイン

```
docker exec -it  myreadthedocs01 bin/bash
```

<blockquote>

Quick start
Assuming you have Python already, install Sphinx:
pip install sphinx
Create a directory inside your project to hold your docs:

```
cd /path/to/project
mkdir docs

# in docker container
/home/docs/$ mkdir docs
```

Run sphinx-quickstart in there:

```
cd docs
sphinx-quickstart
```
This quick start will walk you through creating the basic configuration; in most cases, you can just accept the defaults. When it’s done, you’ll have an index.rst, a conf.py and some other files. Add these to revision control.

Now, edit your index.rst and add some information about your project. Include as much detail as you like (refer to the reStructuredText syntax or this template if you need help). Build them to see how they look:

```
make html
```

Your index.rst has been built into index.html in your documentation output directory (typically _build/html/index.html). Open this file in your web browser to see your docs。
</blockquote>

コンテナの外にでて中身をローカルにコピーする

```
docker cp myreadthedocs01:/home/docs/docs .
```

ローカルからコンテナにコピーするとき

```
docker cp docs myreadthedocs01:/home/docs/docs
```

ブラウザからindex.htmlを開く
