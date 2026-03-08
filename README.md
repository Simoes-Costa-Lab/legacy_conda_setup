# [LEGACY] CUT&RUN Scripts

This repository contains legacy scripts previously used in the Simoes-Costa Lab for CUT&RUN data processing and analysis.

These scripts supported early CUT&RUN experiments in the lab and are preserved to maintain reproducibility of past analyses. The repository is no longer actively maintained and should not be used as the primary pipeline for new projects.

## Status

⚠️ This repository is archived and retained for historical reference.

## Current Workflows

For current pipelines and actively maintained computational infrastructure, please refer to other repositories in the **Simoes-Costa-Lab** organization.

---

Maintained for archival purposes.

# Conda Setup
A repository containing an automatic installation of two different conda environments (py27 and py37) for easy user setup.

## Installation guide (Only first time!)
Clone the repository, make the script executable, and then run it.
```bash
git clone https://github.com/Simoes-Costa-Lab/conda_setup/
cd conda_setup
chmod +x ./install.sh
./install.sh
```
Reload your shell

## Update guide
Update the repository, then update the environment.
```bash
cd conda_setup
git pull
conda env update -n py37 --file py37environment.yml #can --prune if you want.
conda env update -n py27 --file py27environment.yml
```

## Exporting an update guide
Update packages for each environment
```bash
conda update --all
pip list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U 
conda activate py27
conda update --all
pip list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U 
```

Write out the environment to a file
```bash
conda env export -n py37 > py37environment.yml
conda env export -n py27 > py27environment.yml
```
Then upload this to github, don't forget to update the prefix with $HOME.
