# african-rock-python
Covert legacy code to machine-learning Python routines for weather and climate modelling


```bash
ssh -X jpadavatan@dtn.chpc.ac.za
cd /mnt/lustre/users/jpadavatan/
mkdir dev
cd dev/
```

## 2. Set Up the Environment
### Load the necessary modules (Python and CUDA):
```bash
module load chpc/compmech/python/3.11.6-gcc-12.1.0
module load chpc/cuda/12.4/12.4
```
If you prefer using Conda, load the Conda module:
```bash 
module load chpc/compmech/anaconda/3_23.9.0
```

## 3. Clone the Repository
### Clone the mlde repository from GitHub:
```bash
git clone https://github.com/henryaddison/mlde.git
cd mlde
```

## 4. Create a Virtual Environment
### If using Python's venv:
```bash
python -m venv mlde_env
source mlde_env/bin/activate
```
### If using Conda:
```bash
conda create --name mlde_env python=3.8
conda activate mlde_env
```
## 5. Install Dependencies
### Install the required Python packages using pip:
```bash
pip install -r requirements.txt
```
### If there is no requirements.txt file, check the repository's documentation for specific installation instructions. You may need to install dependencies manually, such as:
```bash
pip install numpy pandas scikit-learn torch
```

## 6. Install the mlde Package
### If the repository is a Python package, install it in editable mode:
```bash
pip install -e .
```
This will install the package and make it available in your environment.

## 7. Set Up CUDA and GPU Support
### Ensure CUDA is properly configured for GPU support. Check the available GPUs:
```bash
nvidia-smi
```
### If the project uses PyTorch or TensorFlow, ensure the correct GPU-enabled versions are installed. For example:
```bash
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu112
```


conda --version
conda create -n mlde_env python=3.8

conda init
