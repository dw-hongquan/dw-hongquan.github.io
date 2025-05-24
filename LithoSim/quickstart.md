# Quickstart

**Minimum System Requirements**
- RAM: At least 60GB (80GB Recommended)
- Processor: Multicore with good processing speed
- Python: Version 3.9 or later
- Storage: SSD with ample space for large LithoSim datasets

**LithoSim Benchmark Download**

The first step is to download LithoSim Benchmark [here](https://huggingface.co/datasets/grandiflorum/LithoSim), featuring over 4 million high-resolution input-output pairs with rigorous physical correspondence. The dataset systematically incorporates alterable optical source distributions, metal and via mask topologies with optical proximity correction (OPC) variants, and process windows reflecting fab-realistic variations.

Please unzip all ```*.tar.gz``` file using following command
```
tar -xzvf *.tar.gz
```

Training data corresponds to **train_val** folders (i.e. ```./lithosim/opc_metal/train_val```). Test data corresponds to **test** folders (i.e. in-distribution ```./lithosim/opc_metal/test``` and out-of-distribution ```./lithosim/ood/test```). The training and validation splits can be found at ```train_val_split``` in [```./configs/data/litho.yaml```](https://github.com/dw-hongquan/LithoSim/blob/main/configs/data/litho.yaml).

**Code Download and Environmental Requirements**

Clone the Github repo [here](https://github.com/dw-hongquan/LithoSim) and set your own environment following these commands:

```bash
# clone project
git clone https://github.com/dw-hongquan/LithoSim
cd LithoSim

# [OPTIONAL] create conda environment
conda create -n myenv python=3.9
conda activate myenv

# install pytorch according to instructions
# https://pytorch.org/get-started/

# install requirements
pip install -r requirements.txt
```

If you are prefered to use conda dependences:
```bash
conda install --file environment.yaml
```

**Prepare Dataset Path Files**

LithoSim use ```lithosim_path.txt``` to manage all sub-datasets ([opc_metal](https://huggingface.co/datasets/grandiflorum/LithoSim/viewer/opc_metal), [metal](https://huggingface.co/datasets/grandiflorum/LithoSim/viewer/metal), [opc_via](https://huggingface.co/datasets/grandiflorum/LithoSim/viewer/opc_via), [via](https://huggingface.co/datasets/grandiflorum/LithoSim/viewer/via), [ood](https://huggingface.co/datasets/grandiflorum/LithoSim/viewer/ood)). Please use [```./tool/dataset2txt.py```](https://github.com/dw-hongquan/LithoSim/blob/main/tool/dataset2txt.py) and replace ```dataset_dir``` and ```txt_path``` to generate you own path.

```bash
python tool/dataset2txt.py
```

Each line of the ```lithosim_path.txt``` path file will contain 5 components:

```python
source_path mask_path dose_value defocus_value resist_path

# i.e.
/home/hehq/dataset/lithosim/opc_metal/train_val/1/source_simple.src /home/hehq/dataset/lithosim/opc_metal/train_val/1/mask.png 1.0 -40 /home/hehq/dataset/lithosim/opc_metal/train_val/1/RI_1.0_dose_-40_defocus.png
```

**Training and Validation**

Train your model on the training/validation data and test using the test data. Edit ```train_val_path```, ```test_path```, and ```batch_size``` at ```./lithosim/configs/data/litho.yaml```.

**Evaluation**

Evaluation time! Use the [`./tool/litho_eval.py`](https://github.com/dw-hongquan/LithoSim/blob/main/tool/litho_eval.py) to see how your model does! Use the **iou_dice**, **cal_acc**, **cal_mse**, and **EPECalculator** methods in the [`src/models/losses/metrics.py`](https://github.com/dw-hongquan/LithoSim/blob/main/src/models/losses/metrics.py) script to see how your model does on point estimates. 😊