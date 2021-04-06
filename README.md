<!--
<p align="center">
  <img src="docs/source/logo.png" height="150">
</p>
-->

<h1 align="center">
  table_format
</h1>

<p align="center">
    <a href="https://github.com/spookylukey/table-format/actions?query=workflow%3ATests">
        <img alt="Tests" src="https://github.com/spookylukey/table-format/workflows/Tests/badge.svg" />
    </a>
    <a href="https://github.com/cthoyt/cookiecutter-python-package">
        <img alt="Cookiecutter template from @cthoyt" src="https://img.shields.io/badge/Cookiecutter-python--package-yellow" /> 
    </a>
    <a href="https://pypi.org/project/table-format">
        <img alt="PyPI" src="https://img.shields.io/pypi/v/table-format" />
    </a>
    <a href="https://pypi.org/project/table-format">
        <img alt="PyPI - Python Version" src="https://img.shields.io/pypi/pyversions/table-format" />
    </a>
    <a href="https://github.com/spookylukey/table-format/blob/main/LICENSE">
        <img alt="PyPI - License" src="https://img.shields.io/pypi/l/table-format" />
    </a>
    <a href='https://table-format.readthedocs.io/en/latest/?badge=latest'>
        <img src='https://readthedocs.org/projects/table-format/badge/?version=latest' alt='Documentation Status' />
    </a>
</p>

Format Python code (list of lists) as a fixed width table.

## 💪 Getting Started

You've got some tests like this:
```python

def test_the_thing():
    assert do_the_thing() == [
        ["A nice header", "Another", "More"],
        [1, 2, 3],
    ]
```

Wouldn't it be nice if those columns lined up?

Copy the whole list of lists to the clipboard, then pipe to ``table-format --guess-indent``. On Linux you could use `xsel` or `xclip` etc:


### Options

Pass the `--help` flag to show all subcommands:

```shell
$ table-format --help
```

## ⬇️ Installation

<!-- Uncomment this section after your first ``tox -e finish``
The most recent release can be installed from
[PyPI](https://pypi.org/project/table-format/) with:

```bash
$ pip install table-format
```
-->

The most recent code and data can be installed directly from GitHub with:

```bash
$ pip install git+https://github.com/spookylukey/table-format.git
```

To install in development mode, use the following:

```bash
$ git clone git+https://github.com/spookylukey/table-format.git
$ cd table-format
$ pip install -e .
```

## ⚖️ License

The code in this package is licensed under the MIT License.

## 🙏 Contributing
Contributions, whether filing an issue, making a pull request, or forking, are appreciated. See
[CONTRIBUTING.rst](https://github.com/spookylukey/table-format/blob/master/CONTRIBUTING.rst) for more information on getting
involved.

## 🍪 Cookiecutter Acknowledgement

This package was created with [@audreyfeldroy](https://github.com/audreyfeldroy)'s
[cookiecutter](https://github.com/cookiecutter/cookiecutter) package using [@cthoyt](https://github.com/cthoyt)'s
[cookiecutter-python-package](https://github.com/cthoyt/cookiecutter-python-package) template.

## 🛠️ Development

The final section of the README is for if you want to get involved by making a code contribution.

### ❓ Testing

After cloning the repository and installing `tox` with `pip install tox`, the unit tests in the `tests/` folder can be
run reproducibly with:

```shell
$ tox
```

Additionally, these tests are automatically re-run with each commit in a [GitHub Action](https://github.com/spookylukey/table-format/actions?query=workflow%3ATests).

### 📦 Making a Release

After installing the package in development mode and installing
`tox` with `pip install tox`, the commands for making a new release are contained within the `finish` environment
in `tox.ini`. Run the following from the shell:

```shell
$ tox -e finish
```

This script does the following:

1. Uses BumpVersion to switch the version number in the `setup.cfg` and
   `src/table-format/version.py` to not have the `-dev` suffix
2. Packages the code in both a tar archive and a wheel
3. Uploads to PyPI using `twine`. Be sure to have a `.pypirc` file configured to avoid the need for manual input at this
   step
4. Push to GitHub. You'll need to make a release going with the commit where the version was bumped.
5. Bump the version to the next patch. If you made big changes and want to bump the version by minor, you can
   use `tox -e bumpversion minor` after.
