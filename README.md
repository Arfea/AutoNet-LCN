This repo is forked and modified from https://github.com/awni/ecg.git

## Install 

Clone the repository

```
git clone https://github.com/Arfea/ecg.git
```

If you don't have `virtualenv`, install it with

```
pip install virtualenv
```

Make and activate a new Python 2.7 environment

```
virtualenv -p python2.7 ecg_env
source ecg_env/bin/activate
```

Install the requirements (this may take a few minutes).

For CPU only support run
```
./setup.sh
```

To install with GPU support run
```
env TF=gpu ./setup.sh
```
## Download ICBEB dataset
For illustration purpose, we demonstrate the LCN benchmarked with ResNet-based model by [Hannun et al.](https://www.nature.com/articles/s41591-018-0268-3) on the [ICBEB 2018 Challenge](http://2018.icbeb.org/Challenge.html).

You can also download the datasets by running the relevant cells in the notebook (see below).

## Run the notebook
Run `ecg/ecg/icbeb.ipynb` cell by cell. Be careful that the command `build_json()` should only be run once and the kernel needs to be restarted before running the subsequent codes, to avoid out-of-memory errors.

So far the `autonet(params)` function cannot be directly called in the notebook due to memory constraints, as the kernel needs to be restarted every time `train_hannun_model(params)`, `train_LCN(params)`, `evaluate_hannun(params)`, or `evaluate(params)` is called. Instead, one needs to adjust the hyperparameters (`repeat`, `skip`, `bn`) manually according to the `autonet(params)` algorithm.





