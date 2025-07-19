# Python Package Template
Last updated: 2025-07-19

## Using the Template
1. Clone this repository.
2. Rename all instances of `python_template` to your new package name.
   - Folder `src/python_template` -> `src/<new_name>`
   - Folder `tests/test_python_template` -> `tests/test_<new_name>`
   - In `pyproject.toml`
      - Package name `name = "python_template"` -> `name = "<new_name>"`
      - Package version `version = {attr = "python_template.__version__"}` -> `version = {attr = "<new_name>.__version__"}`
   - In this file, `src/python_template/__init__.py` -> `src/<new_name>/__init__.py` in the `Version Bumping` section below.
3. In `pyproject.toml`, update the package metadata: description, authors, etc.

## Installation
1. Install [uv](https://github.com/astral-sh/uv) for your system.
2. Install [make](https://www.gnu.org/software/make/) for your system.
3. Clone this repository and `cd` into it.
4. Run `uv venv --python 3.13` to initialize a virtual environment with Python 3.13.
5. Activate your new virtual environment.
   - If you're using an IDE, select the virtual environment as your
default Python interpreter, then restart the terminal.
6. Run `make install` to install all requirements, or `make dev_install` to also include optional dependencies
required for code formatting, tests, etc.

## Updating Dependencies
1. Edit the `pyproject.toml` manually.
2. Run `make compile`, followed by `make install` or `make dev_install`.

Alternatively, you can use `uv add`/`uv remove` to update dependencies, compile the lock file, and install with a single command.

## Formatting and Tests
1. Follow the `Installation` section above, being sure to use `make dev_install` instead of `make install`.
2. Run `make format` to lint and format all code using `ruff`, then check types using `ty`.
3. Run `make test` to run tests and output a code coverage report.

## Version Bumping
- Edit `__version__` in `src/python_template/__init__.py`
