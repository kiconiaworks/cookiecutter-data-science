# {{cookiecutter.project_name}} README


{{cookiecutter.description}}


This project uses these key technologies:

* python 3.6


## Local Installation


> If you have trouble creating the venv from the commandline, adding through pycharm is recommended

### Install dependencies

```
# prepare virtualenv and install dependencies
pipenv install
pipenv install --dev
```

> When changes are made make sure to commit the 'Pipfile.lock' so the results can be reproduced


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
make mypy
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



Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
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
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
