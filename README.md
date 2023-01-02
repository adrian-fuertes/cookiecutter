# Python project template

 My Python development project template 😄

## Template usage

To get started, install [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/)

```sh
brew install cookiecutter
```

Then create a new project from the cookiecutter template

```sh
cookiecutter gh:adrian-fuertes/cookiecutter
```
A project folder with the inputed name will be created in your current working directory
## Project usage

### Installation

Install [Poetry](https://python-poetry.org)
```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Install the package and other dependencies

```sh
poetry install
```

Install [pre-commit](https://pre-commit.com)

```sh
brew install pre-commit
```

### Dependencies
- Poetry is used to manage code dependencies. Poetry, alongside other tool's configs, is managed through the `pyproject.toml` file
- During development, use `poetry add dependency` to add package dependencies. Use `poetry add dependency --group dev` development dependencies.

### Testing

- [Pytest](https://docs.pytest.org/en/7.2.x/) and [pytest-cov](https://pytest-cov.readthedocs.io/en/latest/) are used for testing.
- Add tests to `/tests` and execute `pytest --cov=.` to run them and assess coverage
- Pytest arguments are defined in `pyproject.toml` and pytest-cov settings are defined in `.coveragerc`
- Required testing coverage is **95%**
- Tests will run on pull requests and when pushing to `main` using Github Workflows

### Formatting
- Formatting is handled by [black](https://github.com/psf/black), with black's parameters set in `pyproject.toml`
- Line length is set to `80` characters
- [isort](https://pycqa.github.io/isort/) is used to sort file imports, with its parameters being defined in `pyproject.toml`
- Staged code is automatically formatted using pre-commit Git hooks


### Linting

- Code linting is handled by [flake8](https://flake8.pycqa.org/en/latest/), with its arguments being defined in `.flake8`
- [Pylint](https://pylint.pycqa.org/en/latest/) is exclusively used to enforce [W0511](https://pylint.pycqa.org/en/latest/user_guide/messages/warning/fixme.html) (this behavior is defined in the pre-commit hook that enforces it)
- [MyPy](https://mypy.readthedocs.io/en/stable/) is used for type checking, with its parameters being defined in `pyproject.toml`
- Flake8, Pylint and MyPy run on the pre-commit hook