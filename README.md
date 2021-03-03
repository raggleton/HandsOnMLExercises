# Hands-On ML Book Exercises / playing

Doing exercises from the book (v2) & playing around

Official reference notebook: https://github.com/ageron/handson-ml2


## Jupyter in a virtual environment

If using a virtualenv, need to explicitly add it to the Jupyter kernels: `python -m ipykernel install --user --name=XXX` where `XXX` is the name of the virtualenv

This ensures it uses the packages in the virtualenv, and not the system python version (check with `plt.__file__`)

You can list the jupyter kernels: `jupyter kernelspec list`


## Blogging / markdown conversion

Use `nbdev` package to do conversion: https://www.fast.ai/2020/01/20/nb2md/

Specifically: `nbdev_nb2md xxxx.ipynb` to create: `xxxx.md` and `xxxx_files`. These can be copied to the website repository.

The `settings.ini` file is required for `nbdev_nb2md`.

## XGBoost installation on Mac

On my Mac, pip needed to compile XGBoost, rather than using the prebuilt wheels. This will error with: 

```
Could NOT find OpenMP_C (missing: OpenMP_C_FLAGS OpenMP_C_LIB_NAMES)
```

clang on a Mac is missing the OpenMP libraries, so let's install it first: ` brew install libomp` (you will also need `cmake`)

`pip install xgboost` should now work fine.

(Note to self: to avoid updating all other homebrew packages can do ` brew install --ignore-dependencies libomp` or `HOMEBREW_NO_AUTO_UPDATE=1 brew install libomp`)

Maybe also see http://stechschulte.net/2016/03/20/openmp-osx-cmake.html, although I didn't follow those steps.