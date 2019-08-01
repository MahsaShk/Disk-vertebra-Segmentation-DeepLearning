# Disk and vertebral segmentation using deep Residual networks

This repository contains information regarding our paper entitled "Inter-vertebral disk modelling from pairs of segmented vertebral models using trainable pre-processing networks". 

# Manuscript abstract
We introduce a combined approach for modelling intervertebral disks based on pairs of neighbouring vertebral models segmented from T2-weighted MRI. Our approach incorporates a trainable pre-processing pipeline using FC-ResNets which demonstrates that a low-capacity fully convolutional network (FCN) can be used as a pre-processor to normalize the input MRI data. In the proposed segmentation pipeline, we use FCNs to obtain normalized images, which are then iteratively refined by means of a FC-ResNet to generate a segmentation prediction of the vertebral bodies and pedicles. Based on neighbouring endplates, intervertebral disks are modelled for disk replacement procedures. Clinical experiments on a dataset totalling 43 patients demonstrates promising results in terms of vertebra segmentation and disk extraction. Quantitative comparison to expert MR segmentation yields a surface accuracy of 1.1 ± 0.8mm, while a comparison to CT annotations yielded an accuracy of 2.2 ± 1.4mm. The results illustrate the strong potential and versatility of the pipeline by achieving accurate segmentations which can be used for surgical procedures. 
Keywords: Spine, Inter-vertebral disks, Segmentation, Residual networks, Fully convolutional networks.

# Dataset

We used two publicly available databases. 

The **first** one is available at http://dx.doi.org/10.5281/zenodo.22304. 

It includes 23 subjects with T2-w turbo spin-echo 3D MR images of the lower spine acquired with a 1.5T Siemens scanner and resampled to a voxel sizeof2×1.25×1.25mm3. For  each  vertebral  body  from T11  to  L5,  a  ground  truth  manual  segmentation  is available online.

The **second** dataset is available at SpineWeb (http://spineweb.digitalimaginggroup.ca/spineweb/index.php?n=Main.Datasets).

This dataset includes T2-w MRI and CT scans for 20 cases with   different   dimensions,   voxel   spacing,   and   intensity ranges. In our study, one subject has to be removed (case 16), for which no lower spine scan was available (only cervical MRI was available). 

For both datasets, an expert radiologist has performed manual annotations on vertebral body and pedicles.  Because cases were anonymized, no information on the presence of pathology was available.

# Method

First, vertabral bodies (and pedicles) are segmented using a Residual network (Figure 1).

Second, 3D surfaces are extracted from each vertebral body (Figure 2). 

Third, each intervertebral disc mesh is modelled based on the endplates of its lower and superior vertebrae (Figure 3). 

![Screenshot](pics/VAE-MLP-white.png "VAE-MLP architecture")

# Citation
If you would like to use cite our work, please cite the following paper.

```
@INPROCEEDINGS{8363768, 
author={M. {Shakeri} and I. {Nahle} and E. {Finley} and S. {Kadoury}}, 
booktitle={2018 IEEE 15th International Symposium on Biomedical Imaging (ISBI 2018)}, 
title={Inter-vertebral disk modelling from pairs of segmented vertebral models using trainable pre-processing networks}, 
year={2018}, 
volume={}, 
number={}, 
pages={1122-1125},  
doi={10.1109/ISBI.2018.8363768}, 
ISSN={1945-8452}, 
month={April},}





