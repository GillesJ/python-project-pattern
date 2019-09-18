# Python Best Practices Cookiecutter

Best practices [cookiecutter](https://github.com/audreyr/cookiecutter) template as described in this [blogpost](https://sourcery.ai/blog/python-best-practices/).

## Features
- Testing with [pytest](https://docs.pytest.org/en/latest/)
- Formatting with [black](https://github.com/psf/black)
- Import sorting with [isort](https://github.com/timothycrosley/isort)
- Linting with [flake8](http://flake8.pycqa.org/en/latest/)
- Git hooks that run all the above with [pre-commit](https://pre-commit.com/)

## Tools required globally
- pyenv: set global and local python version
- pipx: manage python-based command line tools
- pipenv: manage python virtualenvs
- cookiecutter: generate project templates
- hub: extend git functionality for use with Github.com

```sh
# Install latest python version if not updated
# ## Specify version manually:
# pyenv install 3.7.4
# pyenv global 3.7.4
## Or automatically with https://github.com/momo-lab/xxenv-latest
pyenv latest install
pyenv latest global

# Install hub for Github plugin
snap install hub --classic

# Install pipx if pipenv and cookiecutter are not installed
pip install pipx
pipx install pipenv
pipx install cookiecutter
```

## Quickstart
```sh
# Use cookiecutter to create project from this template
pipx run cookiecutter gh:GillesJ/python-project-pattern

# Enter project directory
cd <repo_name>

# Initialise git repo
git init

# Create a new project on GitHub with the name of current directory
hub create -d "Brief project description"

# Install dependencies
pipenv install --dev

# Setup pre-commit and pre-push hooks
pipenv run pre-commit install -t pre-commit
pipenv run pre-commit install -t pre-push
```
