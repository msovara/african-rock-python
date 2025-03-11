# 🐍 African Rock Python
Covert legacy code to machine-learning Python routines for weather and climate modelling 🌍🌦️

## 1. Connect to the Cluster 🔌
### To begin, connect to the Lengau cluster via SSH:
```bash
ssh -X jpadavatan@dtn.chpc.ac.za
cd /mnt/lustre/users/jpadavatan/
mkdir dev
cd dev/
```

## 2. Set Up the Environment ⚙️
### Load the necessary modules (Python and CUDA):
```bash
module purge
module load chpc/compmech/python/3.11.6-gcc-12.1.0
module load chpc/cuda/12.4/12.4
```
If you prefer using Conda, load the Conda module:
```bash 
module load chpc/compmech/anaconda/3_23.9.0
```

## 3. Clone the Repository 📥
### Clone the mlde repository from GitHub:
```bash
git clone https://github.com/henryaddison/mlde.git
cd mlde
```

## 4. Create a Virtual Environment 🛠️
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
## 5.  Install Dependencies 📦
### Install the required Python packages using pip:
```bash
pip install -r requirements.txt
```
### If there is no requirements.txt file, check the repository's documentation for specific installation instructions. You may need to install dependencies manually, such as:
```bash
pip install numpy pandas scikit-learn torch
```

## 6. install the mlde Package 📂
### If the repository is a Python package, install it in editable mode:
```bash
pip install -e .
```
This will install the package and make it available in your environment.

## 7. Set Up CUDA and GPU Support 🎮
### Ensure CUDA is properly configured for GPU support. Check the available GPUs:
```bash
nvidia-smi
```
### If the project uses PyTorch or TensorFlow, ensure the correct GPU-enabled versions are installed. For example:
```bash
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu112
```
## 8. Test the Installation 🧪
### Run a small test or example script from the repository to verify the installation. For example:
```bash
python examples/example_script.py
```

## 9. Submit a Job (Optional) 🚀
### If you need to run the project as a job on the cluster, create a job script (e.g., job_script.sh):
```bash
#!/bin/bash
#PBS -N nameyourjob
#PBS -q gpu_1
#PBS -l select=1:ncpus=4:ngpus=1
#PBS -P PRJT1234
#PBS -l walltime=4:00:00
#PBS -m abe
#PBS -M your.email@address

module purge
module load chpc/compmech/python/3.11.6-gcc-12.1.0
module load chpc/cuda/12.4/12.4

cd $PBS_O_WORKDIR
source mlde_env/bin/activate  # or conda activate mlde_env

python your_script.py
```
Submit the job:

```bash
qsub job_script.sh
```

## 10.  Monitor the Job 👀
### Check the status of your job:
```bash
qstat -u your_username
```

## Troubleshooting 🔧
### If you encounter errors, check the following:
✅ Ensure all dependencies are installed correctly.

✅ Verify that the correct versions of Python, CUDA, and libraries are being used.

✅ Check the repository's documentation or issues page for additional guidance.
