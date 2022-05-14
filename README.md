## Adaboost Teacher 

The method is designed for domain adaptation segmentation. It also can be applied on semi-supervised Cifar-10.

### Mean Teacher Baseline
```bash
python -m experiments.cifar10_test
```

### Ours
```bash
python -m experiments.ada_cifar10_alpha2
```

### Results
We run all experiments 10 times for a fair comparison.  
It is slightly different in our paper.

CIFAR-10 using 4000 labels   | test error
-----------------------------|-----------
CT-GAN [\[paper\]](https://openreview.net/forum?id=SJx9GQb0-) | 9.98 ± 0.21
Mean Teacher ResNet-26	     | **6.28 ± 0.15**
Mean Teacher ResNet-26 (Our Re-implementation with 3 GPU)      | **6.14 ± 0.24**
Adaboost Teacher ResNet-26       | **6.05 ± 0.12**
All labels, state of the art [\[paper\]](https://arxiv.org/abs/1705.07485) | 2.86
