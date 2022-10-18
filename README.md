# packaging_srund_test
Following the Python packaging tutorial.

As described by [this link](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

## Stages

    1.  Making a simple Python module. Naming and content roughly what the
        tutorial suggest.
    2.  Project toml-file. Choosing `setuptools` as build system as I have
        personally seen it in actual use more often than other systems.
        Filling in other fields appropriately.
        LICENCE was already included in the initial commit.
        Classifiers in the toml-file is something to remember.
    3.  Install `pip` packages `build` and `twine` for build and uploading the
        wheel.
    4.  Generated wheel with `python3 -m build` from the project root and
        installed into wheel a virtual environment as a test.
        It works but the module is unpolished and thats fine.
    5.  Test of upload. Retreive API-token from separate test environment
        [test.pypi.org](https://test.pypi.org).
        For production environment use [pypi.org](https://pypi.org).
        Uploading (to test env) with: `python3 -m twine upload --repository testpypi dist/*`
    6.  Prepared another virtual environment and installed with
        `python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps example-package-srund`
        It seem to work! **Basics done!**

### Dependencies

A continuation from the previous section.

Following [this](https://setuptools.pypa.io/en/latest/userguide/dependency_management.html)
page for `setuptools`.

    1.  Adding basic dependency `click` in the toml-file.
    2.  Manually building the package and installing into a virtual environment
        to confirm `click` is indeed installed together with the package.
