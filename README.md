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