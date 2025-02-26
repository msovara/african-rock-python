# african-rock-python
Covert legacy code to machine-learning Python routines for weather and climate modelling


```bash
ssh -X jpadavatan@dtn.chpc.ac.za
cd /mnt/lustre/users/jpadavatan/
mkdir dev
cd dev/

module avail 2>&1 | grep -i python
module load chpc/compmech/python/3.11.6-gcc-12.1.0
module load chpc/python/anaconda/3-2024.10.1

conda --version
conda create -n mlde_env python=3.8

conda init

```
