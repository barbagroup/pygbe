# Developer's Guide

Welcome to PyGBe's developer's guide!  This is a place to keep track of information that does not belong in a regular userguide.  

## Contributing to PyGBe

All code must go through the pull request review procedure.  
If you want to add something to PyGBe, first fork the repository.  Make your changes on your fork of the repository and then open a pull request with your changes against the main PyGBe repository.  

New features should follow the following rules:
1. PEP8 style guide should be followed
2. New features should include unit tests 
3. All functions should have NumPy style doctrings.  See [here](https://github.com/numpy/numpy/blob/master/doc/HOWTO_DOCUMENT.rst.txt) for reference)

## Running the tests

PyGBe currently only has regression tests.  
Once everything is installed, you can navigate to `pygbe/tests/regression_tests`.  
To run any of the regression tests individually, just run the corresponding script.

```python
python lysozyme.py
```

or to run all of the tests, use the helper script

```python
python run_all_regression_tests.py
```

## Generating documentation

Ensure `sphinx` is installed.  

```console
$ pip install sphinx
$ conda install sphinx
```

Once you have added docstrings to some new functions, first reinstall PyGBe using either 

```console
$ python setup.py install
```

or

```console
$ python setup.py develop
```

In the root of `pygbe` run 

```console
$ sphinx-apidoc -f -o docs/source pygbe
```

Then enter the docs folder and run `make`

```console
$ cd docs
$ make html
```

Ensure that the docs have built correctly and that formatting, etc, is functional by opening the local docs in your browser

```console
firefox _build/html/index.html
```

If there are any errors in the build (or warnings), then fix them.
If there are no errors and the docs look good on your local build, then you're done!
Open a PR with your changes and when it is merged, the changes to the documentation will be automatically built and pushed
by Travis to the `gh-pages` branch.