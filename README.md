# Installing `fastai` with `CUDA` support on Ubuntu 24.04

This project is a template for installing `fastai` with `pytorch` with CUDA
support on Ubuntu 24.04.

## Install CUDA 12.8

I used the following instructions to install CUDA 12.8. Note that `nvidia-smi`
in invaluable in determining that the installation worked and for checking
the CUDA version:

  * [https://www.baeldung.com/linux/ubuntu-gpu-cuda]

You should be able to use `nvidia-smi` to see what card you have and what
CUDA version is available.

## Use `uv` to install Python packages

I used `uv pip` to install packages. If you want to use `uv` you will need to
have it available. Check the website. It's simple.

## Create a virtual environment

```
uv venv
```
This command creates a virtual environment under `.venv`. It may activate it
automatically or give you instructions on how to activate it manually.

## Install Pytorch 2.6 for CUDA 12.6

`fastai` doesn't (yet) work with Pytorch versions above 2.6 so you have to
install 2.6 explicitly. It could take a long time but `uv` gives you nice
progress bars so at least you know it's working.

```
uv pip install torch==2.6.0 torchvision==0.21.0 torchaudio==2.6.0 --index-url https://download.pytorch.org/whl/cu126
```

## Verify that `CUDA` is available to `pytorch`:

./torch_cuda_test.py

It should print:
```
CUDA available: True
```

## Install fastai 2.8.1

Install `fastai` version 2.8.1 with the following:

```
uv pip install "fastai==2.8.1"
```

## Verify that `fastai` is working

Use the following to get some confidence that `fastai` is working. If it throws
an exception it has failed. Otherwise, it will print a success message.

```
./fastai_test.py
```

It should print:
```
Looking good because no exception was thrown
```
