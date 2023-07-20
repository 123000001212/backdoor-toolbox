# Backdoor Toolbox (MNIST fork)

进度：测试仓库代码能否正确运行；mnist/gtsrb

## ABOUT

This is a fork adding MNIST dataset to the original [backdoor-toolbox](https://github.com/vtu81/backdoor-toolbox) repository. Note that we transform MNIST images to 3\*32\*32 from 1\*28\*28 in preprocessing procedure.

Note: Only "badnet" attack and "NC" defense is tested, I'm not sure if other attack and defenses with MNIST is able to run. 

## Environment setup

- python 3.8.16
- torch 1.13.1
- torchvision 0.14.0
- numpy 1.21.5
- matplotlib 3.5.1

## USAGE

```
# Create a clean set
python create_clean_set.py -dataset=mnist

# Create a poisoned training set
python create_poisoned_set.py -dataset=mnist -poison_type=badnet -poison_rate=0.01

# Train on the poisoned training set
python train_on_poisoned_set.py -dataset=mnist -poison_type=badnet -poison_rate=0.01

# Test the backdoor model
python test_model.py -dataset=mnist -poison_type=badnet -poison_rate=0.01

# Defenses (NC)
python other_defense.py -defense=NC -dataset=mnist -poison_type=badnet -poison_rate=0.01 -no_aug

```

See README_ori.md for more details.

