# Installed CUDA 12.8

https://www.baeldung.com/linux/ubuntu-gpu-cuda

# Installed Pytorch 2.6 for CUDA 12.6

uv pip install torch==2.6.0 torchvision==0.21.0 torchaudio==2.6.0 --index-url https://download.pytorch.org/whl/cu126

# Verified it works with:

./torch_cuda_test.py

# Install fastai 2.8.1

uv pip install "fastai==2.8.1"
