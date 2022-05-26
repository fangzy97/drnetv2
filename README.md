# DRNet

This is the implementation of the DRNet* mentioned in paper "DRNet: Double Recalibration Network for Few-Shot Semantic Segmentation". The origin DRNet is in [here](https://github.com/fangzy97/drnet)

## Usage

### Dependencies
- Python 3.7
- Pytorch 1.6.0
- CUDA 10.1
- tqdm 4.61.0
- PyYAML 5.4.1
- pycocotools 2.0.2

### Dataset
* Pascal-5<sup>i</sup>: [VOC2012](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/) + [SBD](http://home.bharathh.info/pubs/codes/SBD/download.html)
* COCO-20<sup>i</sup>: [COCO2014](https://cocodataset.org/#download)

### Models

We provide trained Models with the ResNet-50 backbone on Pascal-5<sup>i</sup> and COCO-20<sup>i</sup> for performance evalution.

### Scripts

- Change the data_root in `.yaml` files in `data/config`.
- **train**
  
  Running the training script
  ```
  ./tool/train.sh ${DATASET_NAME} drnetv2 ${SPLIT}_resnet50 ${GPU}
  ```
  For example, you can train the drnetv2 on the *split0* of the *Pascal-5<sup>i</sup>* on *gpu 0* by this command:
  ```
  ./tool/train.sh pascal drnetv2 split0_resnet50 0
  ```

- **test**
  
  Running the test script
  ```
  ./tool/test.sh ${DATASET_NAME} drnetv2 ${SPLIT}_resnet50 ${GPU}
  ```
  For example, you can test the drnetv2 on the *split0* of the *Pascal-5<sup>i</sup>* on *gpu 0* by this command:
  ```
  ./tool/test.sh pascal drnetv2 split0_resnet50 0
  ```

## Reference

This repo is mainly built based on [PFENet](https://github.com/dvlab-research/PFENet), [RePRI](https://github.com/mboudiaf/RePRI-for-Few-Shot-Segmentation), and [SemSeg](https://github.com/hszhao/semseg). Thanks for their great work!