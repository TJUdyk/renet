<div align="center">
  <h1>Relational test trest Embedding for Few-Shot Classification <br> (ICCV 2021)</h1>
</div>

## :scroll: 高级人工智能作业  &#x1F308; 
* 尝试针对这个项目进行一些测试和修改
* 尝试使用Visual Transformer的进行修改这个项目
* 结合SSFormer对support和query进行修改


## :heavy_check_mark: Requirements
Ubuntu 16.04
* Python 3.7
* [CUDA 11.0](https://developer.nvidia.com/cuda-toolkit)
* [PyTorch 1.7.1](https://pytorch.org) 1.0.1版本也可以跑
* enipos 0.3.2 
* torch 1.0.1
* torchvision 0.2.2
* wandb 0.12.6
* tqdm 4.62.3

## :gear: Conda environmnet installation
```bash
conda env create --name renet_iccv21 --file environment.yml
conda activate renet_iccv21
```

## :books: Datasets
```bash
cd datasets
bash download_miniimagenet.sh
bash download_cub.sh
bash download_cifar_fs.sh
bash download_tieredimagenet.sh
```

## :deciduous_tree: Authors' checkpoints

```bash
cd checkpoints
bash download_checkpoints_renet.sh
```
The file structure should be as follows:


    
    renet/
    ├── datasets/
    ├── model/
    ├── scripts/
    ├── checkpoints/
    │   ├── cifar_fs/
    │   ├── cub/
    │   ├── miniimagenet/
    │   └── tieredimagenet/
    train.py
    test.py
    README.md
    environment.yml
    
    
    
   
## :pushpin: Quick start: testing scripts
To test in the 5-way K-shot setting:
```bash
bash scripts/test/{dataset_name}_5wKs.sh
```
For example, to test ReNet on the miniImagenet dataset in the 5-way 1-shot setting:
```bash
bash scripts/test/miniimagenet_5w1s.sh
```

## :fire: Training scripts
To train in the 5-way K-shot setting:
```bash
bash scripts/train/{dataset_name}_5wKs.sh
```
For example, to train ReNet on the CUB dataset in the 5-way 1-shot setting:
```bash
bash scripts/train/cub_5w1s.sh
```
训练的记录参考：https://wandb.ai/tjudyk

![](https://github.com/TJUdyk/renet/blob/main/%E8%AE%AD%E7%BB%83%E8%AE%B0%E5%BD%95.png)

Training & testing a 5-way 1-shot model on the CIFAR dataset using 4 NVIDIA 2080Ti GPU takes **7.29h left**.

Training & testing a 5-way 5-shot model on the CIFAR dataset using 4 NVIDIA 2080Ti GPU takes **4.32h left**.

Training & testing a 5-way 1-shot model on the CUB dataset using 4 NVIDIA 2080Ti GPU takes **1.7h**.

Training & testing a 5-way 5-shot model on the CUB dataset using 4 NVIDIA 2080Ti GPU takes **1.16h**.

Training & testing a 5-way 1-shot model on the ImageNet dataset using 4 NVIDIA 2080Ti GPU takes **5.45h**.

Training & testing a 5-way 5-shot model on the ImageNet dataset using 4 NVIDIA 2080Ti GPU takes **2.61h**.

## :art: Few-shot classification results
Experimental results on few-shot classification datasets with ResNet-12 backbone. We report average results with 2,000 randomly sampled episodes.


<table>
  <tr>
    <td>datasets</td>
    <td colspan="2" align="center">miniImageNet</td>
    <td colspan="2" align="center">tieredImageNet</td>
  </tr>
  <tr>
    <td>setups</td>
    <td>5-way 1-shot #24</td>
    <td>5-way 5-shot #19</td>
    <td>5-way 1-shot #16</td>
    <td>5-way 5-shot #18</td>
  </tr>
  <tr>
    <td>accuracy</td>
    <td align="center">67.60</td>
    <td align="center">90.42666/81.554</td>
    <td align="center">71.61</td>
    <td align="center">85.28</td>
    
  </tr>
  <tr>
    <td>accuracy_2channel_SCR</td>
    <td align="center">67.96</td>
    <td align="center">82.13</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_3*3kernel</td>
    <td align="center">66.397</td>
    <td align="center">82.533</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_3channel_SCR</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_ViTTransformer</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_SSF-Transformer</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_CCT-Transformer</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
</table>

<table>
  <tr>
    <td>datasets</td>
    <td colspan="2" align="center">CUB-200-2011</td>
    <td colspan="2" align="center">CIFAR-FS</td>
  </tr>
  <tr>
    <td>setups</td>
    <td>5-way 1-shot #15</td>
    <td>5-way 5-shot #14</td>
    <td>5-way 1-shot #12</td>
    <td>5-way 5-shot #7</td>
  </tr>
  <tr>
    <td>accuracy</td>
    <td align="center">79.49</td>
    <td align="center">91.11</td>
    <td align="center">74.51</td>
    <td align="center">86.60</td>
  </tr>
  <tr>
    <td>accuracy_2channel_SCR</td>
    <td align="center">79.908</td>
    <td align="center">91.9</td>
    <td align="center">74.38532/65.527</td>
    <td align="center">87.397</td>
  </tr>
  <tr>
    <td>accuracy_2*3kernel</td>
    <td align="center"><font color="red">81.87</font></td>
    <td align="center">91.037</td>
    <td align="center">74.873</td>
    <td align="center">87.056</td>
  </tr>
  <tr>
    <td>accuracy_3channel_SCR</td>
    <td align="center">待测试</td>
    <td align="center">91.66</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_ViTTransformer</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
  <tr>
    <td>accuracy_SSF-Transformer</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
    <tr>
    <td>accuracy_CCT-Transformer</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
    <td align="center">待测试</td>
  </tr>
</table>


## :mag: Related repos
Our project references the codes in the following repos:

* Zhang _et al_., [DeepEMD](https://github.com/icoz69/DeepEMD).
* Ye _et al_., [FEAT](https://github.com/Sha-Lab/FEAT)
* Wang _et al_., [Non-local neural networks](https://github.com/AlexHex7/Non-local_pytorch)
* Ramachandran _et al_., [Stand-alone self-attention](https://github.com/leaderj1001/Stand-Alone-Self-Attention)
* Huang _et al_., [DCCNet](https://github.com/ShuaiyiHuang/DCCNet)
* Yang _et al_., [VCN](https://github.com/gengshan-y/VCN)
* chenhaoxing_.,[SSFormer](https://github.com/chenhaoxing/SSFormers)
* yhu01/PT-MAP.,[PT-MAP](https://github.com/TJUdyk/PT-MAP)
* alihassanijr [CCT](https://github.com/SHI-Labs/Compact-Transformers)

## :love_letter: Acknowledgement
* We adopted the main code bases from [DeepEMD](https://github.com/icoz69/DeepEMD)
* CSDN解释的网址：https://blog.csdn.net/qq_42578970/article/details/120875948（2021，10，21）
* 小样本图片分类的榜单：https://paperswithcode.com/task/few-shot-image-classification
