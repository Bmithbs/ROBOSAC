## Installation

### Requirements

* Linux (tested on Ubuntu 18.04)
* Python 3.7
* Anaconda
* PyTorch
* CUDA 11.7

### Create Anaconda Environment from yml

in the directory of `ROBOSAC`:

```bash
cd coperception
conda env create -f environment.yml
conda activate coperception
```

### CUDA

```bash
conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
```

### Install CoPerception Library

This installs and links `coperception` library to code in `./coperception` directory.

```bash
pip install -e .
```

### Dataset Preparation

Please download the official [V2X-Sim Dataset](https://ai4ce.github.io/V2X-Sim/download.html)**(<u>V2.0</u>)**

See the [documentation of installing V2X-Sim](https://coperception.readthedocs.io/en/latest/datasets/v2x_sim/) for dataset pre-processing details.


### Specifying Dataset

Link the test split of V2X-Sim dataset in the default value of argument "**data**"

```bash
/{Your_location}/V2X-Sim/sweeps/test
```

in the `test` folder data are structured like:

```
test
├──agent_0
├──agent_1
├──agent_2
├──agent_3
├──agent_4
├──agent_5
      ├──19_0
	  ├──0.npy		
	  ...
```



### Specifying Victim Detection Model Checkpoint

Link the checkpoint location in the default value of argument "**resume**"

Please download [pre-trained weights](https://drive.google.com/drive/folders/1dGEYIzc5ITFKR0TSZfXPYAIw2GBo4oBT?usp=share_link) and save them in `ROBOSAC/coperception/ckpt/meanfusion` folder.

`epoch_49.pth` is the original victim model without adversarial training.

`epoch_advtrain_49.pth` is the PGD-trained model.
