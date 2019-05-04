# FCOS: Fully Convolutional One-Stage Object Detection

This is an unofficial implementation of [FCOS](https://arxiv.org/abs/1904.01355) in a [gluon-cv](http://gluon-cv.mxnet.io) style, we implemented this anchor-free framework in a fully [Gluon](https://mxnet.incubator.apache.org/versions/master/gluon/index.html) API, please stay tuned! 


## Installation 
1.Install cuda `10.0` and mxnet `1.4.0`.
  ```Shell
  sudo pip3 install mxnet-cu100==1.4.0.post0
  ```
2. Clone the code, and install gluoncv with ``setup.py``.
  ```Shell
  cd fcos-gluon-cv
  sudo python3 setup.py build
  sudo python3 setup.py install
  ```

## Preparation
1.Download `COCO2017` datasets follow the official [tutorials](https://gluon-cv.mxnet.io/build/examples_datasets/mscoco.html#sphx-glr-build-examples-datasets-mscoco-py) and create a soft link.
  ```Shell
  ln -s $DOWNLOAD_PATH ~/.mxnet/datasets/coco
  ```
2.More preparations can refer to [GluonCV](https://gluon-cv.mxnet.io/index.html).

3.All experiments are performed on 8 * 2080ti GPU.

## Training & Validation 
1.Copy the training scripts [here](https://github.com/Angzz/fcos-gluon-cv/blob/master/scripts/detection/fcos/train_fcos.py), then train `fcos_resnet50_v1b_coco` with:
  ```Shell
  python3 train_fcos.py --network resnet50_v1b --gpus 0,1,2,3,4,5,6,7 --num-workers 32 --batch-size 8 --log-interval 10
  ```
2.Copy the eval scripts [here](https://github.com/Angzz/fcos-gluon-cv/blob/master/scripts/detection/fcos/eval_fcos.py), then validate `fcos_resnet50_v1b_coco` with:
  ```Shell
  python3 eval_fcos.py --gpus 0,1,2,3,4,5,6,7 --num-workers 32 --pretrained $SAVE_PATH/XXX.params
  ```
  
## Results
To be updated.

