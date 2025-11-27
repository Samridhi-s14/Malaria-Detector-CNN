# Virtual environment and installation

Steps to create and use the virtual environment for this repo.

1. Create the virtual environment (from the repository root):

```bash
python3 -m venv .venv
```

2. Activate the virtual environment:

```bash
source .venv/bin/activate
```

3. Upgrade packaging tools and install requirements:

```bash
python -m pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
```

4. Quick verification (inside the activated venv):

```bash
python -c "import tensorflow as tf, numpy as np, sklearn, PIL, matplotlib, tensorflow_addons as tfa; print('TensorFlow', tf.__version__); print('numpy', np.__version__)"
```

Notes:
- TensorFlow is large and may take several minutes to download and install.
- If you need GPU support, install a GPU-compatible TensorFlow build matching your CUDA/cuDNN versions.
- If installation fails due to binary/compatibility, try a different Python version (official TF releases support specific CPython versions).

Compatibility note:
- `tensorflow-addons` is optional but version-sensitive. Many `tensorflow_addons` releases support TensorFlow >=2.13 and <2.16. If you keep `tensorflow-addons` in `requirements.txt`, use a TensorFlow release compatible with it (for example `tensorflow==2.15.0`).
- The repository's `requirements.txt` has been updated to pin `tensorflow==2.15.0` and `tensorflow-addons==0.20.0` to avoid the "No module named 'keras.src.engine'" error seen when using newer TensorFlow releases.

If you want me to reinstall packages inside the `.venv` now (downgrading TensorFlow from 2.20 → 2.15), I can run the reinstall command here. It will take several minutes.
