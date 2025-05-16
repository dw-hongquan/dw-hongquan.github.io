# Quickstart

**Minimum System Requirements**
- RAM: At least 60GB (80GB Recommended)
- Processor: Multicore with good processing speed
- Python: Version 3.9 or later
- Storage: SSD with ample space for large LithoSim datasets

**LithoSim Benchmark Download**

The first step is to download LithoSim Benchmark [here](https://huggingface.co/datasets/grandiflorum/LithoSim), featuring over 4 million high-resolution input-output pairs with rigorous physical correspondence. The dataset systematically incorporates alterable optical source distributions, metal and via mask topologies with optical proximity correction (OPC) variants, and process windows reflecting fab-realistic variations.

Please unzip all *.tar.gz file using following command
```
tar -xzvf *.tar.gz
```

Training data corresponds to **train_val** folders (i.e. ```./lithosim/opc_metal/train_val```). Test data corresponds to **test** folders (i.e. ```./lithosim/opc_metal/test``` and ```./lithosim/ood/test```). The training and validation splits can be found at ```train_val_split``` in ```./lithosim/configs/data/litho.yaml```.

**Step 2**

Install the `climsim_utils` python tools, by running the following code from the root of the [GitHub repo](https://github.com/leap-stc/ClimSim/tree/main):

```
pip install .
```

If you already have all `climsim_utils` dependencies (`tensorflow`, `xarray`, etc.) installed in your local environment, you can alternatively run:

```
pip install . --no-deps
```

**Step 3**

Train your model on the training data and validate using the validation data. If you wish to use something like a CNN, you will probably want to separate the variables into channels and broadcast scalars into vectors of the same dimension as vertically-resolved variables. Methods to do this can be found in the [`climsim_utils/data_utils.py`](https://github.com/leap-stc/ClimSim/blob/main/climsim_utils/data_utils.py) script.

**Step 4**

Evaluation time! Use the [`evaluation/main_figure_generation.ipynb`](https://github.com/leap-stc/ClimSim/blob/main/evaluation/main_figure_generation.ipynb) notebook to see how your model does! Use the **calc_MAE**, **calc_RMSE**, and **calc_R2** methods in the [`climsim_utils/data_utils.py`](https://github.com/leap-stc/ClimSim/blob/main/climsim_utils/data_utils.py) script to see how your model does on point estimates and use the `calc_CRPS` method to check how well-calibrated your model is if it's stochastic. 😊