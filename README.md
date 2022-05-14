## Adaboost Teacher (on Cifar-10)

![](https://github.com/layumi/AdaBoost_Seg/blob/master/pipeline.png)


[Adaptive Boosting for Domain Adaptation: Towards Robust Predictions in Scene Segmentation](https://arxiv.org/abs/2103.15685)

The method is designed for domain adaptation segmentation. It also can be applied to the semi-supervised setting on Cifar-10.

### Mean Teacher Baseline
```bash
python -m experiments.cifar10_test
```

### Ours
Here we do not change the original weight averaging setting in MeanTeacher, but add the adaptive sampler (every 2 epochs update sampler once). 

```bash
python -m experiments.ada_cifar10_alpha2
```

### Results
We run all experiments 10 times for a fair comparison. We only have 3 GPU on one machine, so we re-run the code. 
It is slightly different with the paper.

CIFAR-10 using 4000 labels   | test error
-----------------------------|-----------
CT-GAN [\[paper\]](https://openreview.net/forum?id=SJx9GQb0-) | 9.98 ± 0.21
Mean Teacher ResNet-26	     | **6.28 ± 0.15**
Mean Teacher ResNet-26 (Our Re-implementation with 3 GPU)      | **6.14 ± 0.24**
Adaboost Teacher ResNet-26 (Our Re-implementation with 3 GPU)       | **6.05 ± 0.12**
All labels, state of the art [\[paper\]](https://arxiv.org/abs/1705.07485) | 2.86


### Acknowledge 
This code is largely borrowed from [Mean Teacher](https://github.com/CuriousAI/mean-teacher) for a fair comparison. 
We really appreciate the author to make the implementation open-source!

