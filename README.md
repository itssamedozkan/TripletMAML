TripletMAML: A metric-based model-agnostic meta-learning algorithm for few-shot classification
===
Abstract:This study presents a new algorithm called TripletMAML which extends the Model-Agnostic Meta-Learning (MAML) algorithm from a metric-learning perspective. The same optimization procedure of MAML is adopted, but the neural network model is replaced with a triplet network which enables the utilization of metric-learning through the embeddings. In order to be able to incorporate the metric loss during meta-learning, we have developed a triplet-task generation scheme that creates tasks consisting of triplets for both $1$-shot and $5$-shot settings. To the best of our knowledge, TripletMAML is the first meta-learning algorithm that is both an optimization-based and a metric-based method for few-shot image classification. We have investigated the performance of TripletMAML which is trained using a loss function that combines a classification and a metric loss on four few-shot image classification benchmarks and compared its performance to several baseline methods. The experimental results yield that TripletMAML with no data augmentation and no hyper-parameter tuning improves MAML by a large margin, and also outperforms all other baseline methods in both $1$-shot and $5$-shot settings. Please note that in all of those experiments, TripletMAML is trained from scratch using the tasks consisting of triplets. We have also shown that the performance of TripletMAML can be further improved via hyper-parameter optimization, and it can achieve competitive results with complex state-of-the-art algorithms. As a future study, we are planning to develop a new version of TripletMAML for few-shot image retrieval problems.

## Paper Information
- Title:  `TripletMAML: A metric-based model-agnostic meta-learning algorithm for few-shot classification`
- Authors:  `Ayla Gülcü`,`Zeki Kuş`,`İsmail Taha Samed Özkan`,`Osman Furkan Karakuş`

## Install & Dependencies
- python  == 3.9.7
- learn2learn == 0.1.7 
- numpy = 1.20.3  
- pytorch == 1.10.2  and  py3.9_cuda11.3_cudnn8.2.0_0 
- scikit-learn == 1.2.0

## Dataset Preparation
![Datasets Visualization](./Images/Datasets.png)
| Dataset | Download | Download Needed |
| ---     | ---      | ---             |
| Omniglot | [download](https://github.com/brendenlake/omniglot) | NO |
| MiniImageNet | [download](https://www.kaggle.com/datasets/arjunashok33/miniimagenet) | NO |
| CUB-200-2011 | [download](https://data.caltech.edu/records/65de6-vp158/files/CUB_200_2011.tgz?download=1) | YES |
| CIFAR Few-Shot | [download](https://drive.google.com/u/1/uc?id=1pTsCCMDj45kzFYgrnO67BWVbKs48Q3NI&export=download) | YES |

- for Omniglot
  ```
  TripletOmniglot.py Files will handle downloading automatically if download mode is set as True.
  ```
- for MiniImageNet
  ```
  ./data/MiniImageNet/MiniImageNet_downloader.py will handle downloading test-train-validation files accordingly. 
  No needed to install another dataset.
  ```
- for CUB-200-2011
  ```
  CUB-200-2011 files are needed to be downloaded from given link. Then replaced into corresponding folder which is ./data/CUB/
  Choose the generator of your preference so they can create the test-train-validation files accordingly.
  ```
- for CIFAR Few-Shot
  ```
  CIFAR Few-Shot files are needed to be downloaded from given link. Then replaced into corresponding folder which is ./data/CIFARFS100/
  First run the processor then you can use generator to create the test-train-validation files accordingly.
  ```

## Use
- for classification
  ```
  please look into ./TripletMAML/maml_triplet_train_test_val.py
  ```
- for retrieval
  ```
  please look into ./TripletMAML/maml_triplet_test_retrieval.py
  ```

## Directory Hierarchy
```
|—— .gitignore
|—— data
|    |—— Generators
|        |—— CIFARFS100
|            |—— CIFARFS100_generator.py
|            |—— CIFARFS100_processor.py
|        |—— CUB
|            |—— CUB_BB_NoResize_generator.py
|            |—— CUB_BB_Resize_generator.py
|            |—— CUB_NoBB_generator.py
|        |—— Flowers
|            |—— Flowers_generator.py
|        |—— MiniImageNet
|            |—— MiniImageNet_downloader.py
|—— HPO
|    |—— backbone.py
|    |—— de.py
|    |—— losses.py
|    |—— model.py
|    |—— rs.py
|    |—— train.py
|    |—— Triplets
|        |—— TripletCUB.py
|        |—— TripletFlowers.py
|        |—— TripletFSCIFAR100.py
|        |—— TripletMiniImageNet.py
|        |—— TripletOmniglot.py
|        |—— __init__.py
|—— TripletMAML
|    |—— backbone.py
|    |—— losses.py
|    |—— maml_triplet_test_retrieval.py
|    |—— maml_triplet_train_test_val.py
|    |—— TaskControl.ipynb
|    |—— Triplets
|        |—— TripletCUB.py
|        |—— TripletFlowers.py
|        |—— TripletFSCIFAR100.py
|        |—— TripletMiniImageNet.py
|        |—— TripletOmniglot.py
|        |—— __init__.py
```
## Code Details
### Tested Platform
- software
  ```
  OS: Ubuntu 20.04 LTS
  Python: 3.9.7 (anaconda)
  ```
- hardware
  ```
  CPU: Intel(R) Core(TM) i9-10850k CPU @3.60 GHz
  GPU: Nvidia RTX3090 (24GB)
  ```
