# Release information

## Documenting for Release

Due to limitations of pbr, setuptools, and pypi, publishing markdown readme's to PyPi has become unnecessarily time-consuming. However, the same can be said for writing tutorial docs in rst. Therefore, the following documentation process is being used.

During development: Write documentation updates into the README.md

Prior to release:
  1. Install: m2r [markdown-to-rst](https://github.com/miyakogi/m2r)
  2. Execute: `m2r README.md`
  3. Install: [rstcheck](https://github.com/myint/rstcheck)
  4. Execute: `rstcheck README.rst`
  5. Execute: `mv -i README.rst PYPIREADME.rst`


## Release steps

1. `git tag -am "vX.Y.Z" vX.Y.Z`
2. `python3 setup.py sdist bdist_wheel`
3. `python3 -m twine check dist/*`
4. `python3 -m twine upload dist/*`
