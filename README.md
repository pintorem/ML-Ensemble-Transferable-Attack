# ML-Ensemble-Transferable-Attack

## Overview 
In this project, adversarial examples are optimized with the specific objective of simultaneously fooling an ensemble composed of three models from RobustBench (CIFAR-10, L-inf). Subsequently, an evaluation is carried out concerning the effectiveness of such adversarial examples when applied to seven additional robust models. The full implementation and experimental results are available in this Colab [notebook](https://colab.research.google.com/drive/1P7_jvSi2QtocdtqHwY64bHMjDBr1-bii#scrollTo=qy4rRaqyRcTb).

## Features
The adversarial examples are crafted by using three different attacks:
- Fast Gradient Sign Method (FGSM)
- Iterative-Fast Gradient Sign Method (I-FGSM) - a.k.a. PGD
- Momentum Iterative-Fast Gradient Sign Method (MI-FGSM)

## Results
These tests have been performed considering only the first 100 samples of CIFAR-10.

| **Attack**   | **Loss**                 | **Adversarial Examples** | **Attack Success Rate** |
|--------------|--------------------------|-----------------------------|----------------------------|
| FGSM         | Margin loss              | 16                          | 18%                        |
| I-FGSM       | Sum of margin losses     | 19                          | 22%                        |
| MI-FGSM      | Cross Entropy            | 24                          | 28%                        |

The number of samples that transfer to the other seven models is reported below

| **Model**                                         | **FGSM** | **I-FGSM** | **MI-FGSM** |
|--------------------------------------------------|---------:|-----------:|------------:|
| Standard                                         |        5 |          4 |           4 |
| Bartoldson2024Adversarial_WRN-94-16             |        2 |          4 |           5 |
| Amini2024MeanSparse_S-WRN-94-16                 |        2 |          4 |           4 |
| Bartoldson2024Adversarial_WRN-82-8              |        3 |          2 |           5 |
| Debenedetti2022Light_XCiT-M12                   |        9 |          5 |           8 |
| Debenedetti2022Light_XCiT-S12                   |       11 |          6 |          10 |
| Rebuffi2021Fixing_70_16_cutmix_ddpm             |       11 |          5 |           7 |

