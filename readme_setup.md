Install git-lfs: `sudo apt-get install git-lfs`

# Download data
```
mkdir data/raw
git lfs install
git clone https://hf.co/datasets/Cainiao-AI/LaDe
```

# Install env
```
# Python < 3.9 does not work with the required torch version
conda create --prefix ./.venv python=3.9 pip
conda activate ./.venv
export PIP_DEFAULT_TIMEOUT=1200
pip install -r requirements.txt
```

# Troubleshooting
#### cannot import name 'packaging'

Error:
```
ImportError: cannot import name 'packaging' from 'pkg_resources' (/home/dvquy_13_gmail_com/LaDe/stg_prediction/.venv/lib/python3.9/site-packages/pkg_resources/__init__.py)
```

Cause:

Some issues with setuptools==70.0.0

Solution:
```
pip install setuptools==69.5.1
```
Ref: https://github.com/aws-neuron/aws-neuron-sdk/issues/893