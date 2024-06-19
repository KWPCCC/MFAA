# Multi-Feature Attention Attack(MFAA)
Corresponding code to the paper "Enhancing the Transferability of Adversarial Attacks via Multi-Feature Attention"


![image text](https://github.com/KWPCCC/MFAA/blob/main/attention.png "DBSCAN Performance Comparison")


## Requirements

- Python 3.6.3
- Keras 2.2.4
- Tensorflow 1.12.2
- Numpy 1.16.2
- Pillow 4.2.1

# Experiments

#### Introduction

- `Multi-Feature Attention Attack.py` : the implementation for attacks.

- `verify.py` : the code for evaluating generated adversarial examples on different models.

  You should download the  pretrained models from ( https://github.com/tensorflow/models/tree/master/research/slim,  https://github.com/tensorflow/models/tree/archive/research/adv_imagenet_models) before running the code. Then place these model checkpoint files in `./models_tf`.

#### Example Usage

##### Generate adversarial examples:

- FMAA

```
python Multi-Feature Attention Attack.py --model_name resnet_v1_152 --attack_method mfaa --layer_name resnet_v1_152/block2/unit_7/bottleneck_v1/Relu --ens 30 --probb 0.7 --output_dir ./adv/MFAA/
```

##### Evaluate the attack success rate

```
python verify.py --ori_path ./dataset/images/ --adv_path ./adv/MFAA/ --output_file ./log.csv
```


