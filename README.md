# Cookiecutter Data Science

_A logical, reasonably standardized, but flexible project structure for doing and sharing data science work._

# {{cookiecutter.repository_name }}  README

[ADD circleci status badge here](https://circleci.com/docs/2.0/status-badges/)


*Explain the purpose of the repository and project. Tell people why this should be used and what problem it solves*

This project uses these key technologies:

* python 3.6


## Local Installation


### Prepare venv

1. From the commandline:
	```
	python -m venv .venv
	```

> If you have trouble creating the venv from the commandline, adding through pycharm is recommended

### Install dependencies

```
# enter venv
source .venv/bin/activate

pip install -r requirements.txt
pip install -r requirements-dev.txt
```

#### Updating and Freezing Dependencies

For circleci testing the `requirements-all-frozen.txt` file is used to *cache* dependencies to speed up testing.

When the `requirements.txt` file is updated and containing packages are installed, run the following command to update dependencies:
```
pip freeze | sort > requirements-all-frozen.txt
```

> Commit the file when changed!


### Running code quality checks

The following checks are run for this project:
- flake8 (with complexity measure)
- pydocstyle
- pylint
- mypy (type checking)

The above checks can be performed with the following commands:

```
# flake8, pydocstyle
make check

# pylint
make pylint

# mypy
make typecheck
```


### Running tests

This project uses pytest for testing, but a helper function is available in the Makefile.

Run manually

```
pytest -v

# run test with coverage
pytest --cov src/ --cov-report term-missing
```

Run with make
```
make test
```


## Install

*Describe the steps needed to install the project to production*


## Repository Branch Management

[githubflow](https://guides.github.com/introduction/flow/)　branching model is used,
if you have a feature you want to contribute create a `feature/FEATURE-NAME` branch from the "*master*" branch, and issue a Pull-Request to have your feature integrated.



> Derived from [Project homepage](http://drivendata.github.io/cookiecutter-data-science/)


### Requirements to use the cookiecutter template:
-----------
 - Python 3.6
 - [Cookiecutter Python package](http://cookiecutter.readthedocs.org/en/latest/installation.html) >= 1.4.0: This can be installed with pip by or conda depending on how you manage your Python packages:

``` bash
$ pip install cookiecutter
```

or

``` bash
$ conda config --add channels conda-forge
$ conda install cookiecutter
```


### To start a new project, run:
------------

    cookiecutter https://github.com/abeja-inc/cookiecutter-data-science


[![asciicast](https://asciinema.org/a/9bgl5qh17wlop4xyxu9n9wr02.png)](https://asciinema.org/a/9bgl5qh17wlop4xyxu9n9wr02)


### The resulting directory structure
------------

The directory structure of your new project looks like this: 

```
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
│
└── tox.ini            <- tox file with settings for running tox; see tox.testrun.org
```

## Contributing

We welcome contributions! [See the docs for guidelines](https://drivendata.github.io/cookiecutter-data-science/#contributing).

### Installing development requirements
------------

    pip install -r requirements.txt

### Running the tests
------------

    py.test tests
