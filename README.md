# Documentation for Python Mini App

## Installation

First make sure you have python and pip installed:

```shell
$ python --version
Python 2.7.9
$ pip --version
pip 8.1.1
```

Then use pip to install mkdocs

```shell
$ pip install mkdocs
```

Now you should have ```mkdocs``` in your command line:

```shell
$ mkdocs --version
mkdocs, version 0.15.3
```


## View your change locally

After you make some changes, to view the whole site, use:

```shell
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
Serving on http://127.0.0.1:8000
```

or simply use:

```shell
$ ./runserver.sh
INFO    -  Building documentation...
INFO    -  Cleaning site directory
Serving on http://127.0.0.1:8000
```

Now you can see the whole site at ```http://127.0.0.1:8000```.

Once you finished all the changes, commit & push your changes.

## Deploy

To deploy to product server, just run:

```shell
$ ./deploy.sh
```

You will see the published site in a few seconds.


## Reference:

* [Mkdocs](http://www.mkdocs.org/)
* [mkdocs.yml](http://www.mkdocs.org/user-guide/configuration/)
* [Deploying docs](http://www.mkdocs.org/user-guide/deploying-your-docs/)
