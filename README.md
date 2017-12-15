# GLAD
This repository provides the code for our ACM MM17 paper [GLAD: Global-Local-Alignment Descriptor for Pedestrian Retrieval](https://arxiv.org/pdf/1709.04329.pdf)

![](https://github.com/JoinWei-PKU/GLAD/blob/master/framework.png)

### Step.1 Pose Estimation
The first stage is to estimate the human keypoint.
We used the deepercut model provided in [DeeperCut](https://github.com/eldar/deepcut). Especially, we utilize the single person pose estimation model.

Afer pose estimation, please cut the three parts according to our paper. Examples images as followes:
![](https://github.com/JoinWei-PKU/GLAD/blob/master/datasets/example1.jpg) ![](https://github.com/JoinWei-PKU/GLAD/blob/master/datasets/example2.jpg)

You can utilize any pose estimation methods to replace DeeperCut.

### Step.2 Descriptor Learning
### Dataset
Download [Market1501 Dataset](http://www.liangzheng.org/Project/project_reid.html). Then process these raw data as step.1

### ImageNet Pretrained model
Download [GoogLeNet model](https://github.com/lim0606/caffe-googlenet-bn) pretrained on Imagenet.

### Train our GLAD
1. Modify the `prototxt\train_val.prototxt`. Please modify the dataset path in the file.

2. Begin training with 10,0000 iterations. 

## Test 
1. Extract fc6(and layer1/fc6, layer2/fc6, layer3/fc6) features.
2. L1 normalization and add weights according our paper.

### Citation
Please cite this paper in your publications if it helps your research:
```
@inproceedings{wei2017glad,
  title={GLAD: Global-Local-Alignment Descriptor for Pedestrian Retrieval},
  author={Wei, Longhui and Zhang, Shiliang and Yao, Hantao and Gao, Wen and Tian, Qi},
  booktitle={ACM MM},
  year={2017}
}
```
