# Accelerator-Aware-Pruning (AAP)

[![License](https://img.shields.io/badge/license-BSD-blue.svg)](LICENSE)

By [Hyeong-Ju Kang](http://)

## Introduction

Accelerator-aware pruning(AAP) is a pruning scheme that considers an acceleartor
	structure.
With accelerator-aware pruning, you can imporove the operator utilization
	of the sparse NN accelerators like Cambricon-X and EIE,
	and can design a sparse NN accelerator with much lower complexity.
For more details, please refer to my [arXiv paper](http://arxiv.org/abs/1804.09862)
	or [the version](https://ieeexplore.ieee.org/document/8693518) published in IEEE Transactions on
	Circuits and Systems for Video Technology.

## Citing AAP

Please cite AAP in your publications if it helps your research:

	@article{hjkang2020aap,
		author = {Kang, Hyeong-Ju},
		title = {Accelerator-Aware Pruning for Convolutional Neural Networks},
		journal = {IEEE Transactions on Circuits and Systems for Video Technology},
		volume = {30},
		number = {7},
		pages = {2093--2103},
		month = {July},
		year = {2020}
	}

## Pruned Models
More pruned models will be uploaded here soon.

### Classification CNNs
In the following models, only convolutional layers are pruned.

| CNNs		| g	| p	| top-5 | pruned models |
|-------	|---|---|------:|--------|
| AlexNet\*	| 8	| 6	| 80.42%			|[caffemodel](https://drive.google.com/file/d/1hfCuoY8mXXl4noi_fAt-Xx65N2hSAens/view?usp=sharing)
| VGG 16	| 8	| 6	| 89.91%			|[caffemodel](https://drive.google.com/file/d/19kmLWVdC0dwvByrq-CIXLFG_y8q-2RLy/view?usp=sharing)
| ResNet-50	| 8	| 6	| 91.14%			|[caffemodel](https://drive.google.com/file/d/1wsnddvFOJzOJQabYanK8mJTfA4qpm_DG/view?usp=sharing)
| ResNet-152| 8	| 6	| 92.33%			|[caffemodel](https://drive.google.com/file/d/1Ej08Wzo7wQOPbsfpJ4NRWPQGmRpiNxYs/view?usp=sharing)
| AlexNet\*		| 16| 12| 80.50%		|[caffemodel](https://drive.google.com/file/d/1jbwMnw2oXOv6jNZc-GsOGpc4Dy5MFAC9/view?usp=sharing)
| VGG 16		| 16| 12| 90.22%		|[caffemodel](https://drive.google.com/file/d/1JHCM1ZOWQ4ELMDYleDUCg35pCHF2EQqa/view?usp=sharing)
| ResNet-50		| 16| 12| 91.35%		|[caffemodel](https://drive.google.com/file/d/1hk6HK5dor5dsfm-mj_9sT4NPvK8uJ07I/view?usp=sharing)
| ResNet-152	| 16| 12| 92.48%		|[caffemodel](https://drive.google.com/file/d/1ZMU764yrPbOoFVWR2i4aHneaNdKkVera/view?usp=sharing)
| SqueezeNet v1	| 16| 10| 80.29%		|[caffemodel](https://drive.google.com/file/d/1cyLBaCzN8n9JFSpFVD9VUzNw9YlhCMiR/view?usp=sharing)
| SqueezeNet v1	| 16| 12| 78.80%		|[caffemodel](https://drive.google.com/file/d/1lUM4dz5hvV25eMgKUKJooGs5Clp4I4Ua/view?usp=sharing)
| MobileNet v1	| 16| 10| 89.79%		|[caffemodel](https://drive.google.com/file/d/1dAtA9ao0bqXBobpJu4a5ZwuTVMPIhMx9/view?usp=sharing)
| MobileNet v1	| 16| 12| 89.06%		|[caffemodel](https://drive.google.com/file/d/1kuFBeAaHRW4PHWUBktj4IJR3uzO6RQMs/view?usp=sharing)

\* No LRN was used in AlexNet.
[prototxt](https://drive.google.com/file/d/1EytqXiBdhqm1coD6jmyDeY6qr6xp5NoP/view?usp=sharing)
[caffemodel](https://drive.google.com/file/d/1EXLi9WwaU-9qQhLL1hSBGF7qP7jl58Dt/view?usp=sharing)

In the following models, fully connected layers are pruned, too.
| CNNs		| g	| p<sub>conv</sub>| p<sub>fc1,2</sub>| p<sub>fc3</sub>| top-5 | pruned models |
|-------	|---|-----------------|------------------|----------------|------:|--------|
| AlexNet\*	| 16| 12| 15| 12| 79.47%			|[caffemodel](https://drive.google.com/file/d/1_4lbvs5qcPFrmwpl7UOfmGRACGF_eLD1/view?usp=sharing)
| VGG 16	| 16| 12| 15| 12| 88.95%			|[caffemodel](https://drive.google.com/file/d/1RNZDQzehI4AHpjskJ5rRLKcrmnv955LW/view?usp=sharing)
| ResNet-50 | 16| 12| - | 12| 91.24%			|[caffemodel](https://drive.google.com/file/d/18IQ_AA5dw3cMXxNueJA0bBr04xJBOZRk/view?usp=sharing)
| ResNet-152| 16| 12| - | 12| 92.54%			|[caffemodel](https://drive.google.com/file/d/1I3NSvUVY0X5bWyo_1mkgg-V_4On73MF1/view?usp=sharing)

### Object Detection CNNs
AAP can be applied to object detection CNNs, too.
The following models are object detection CNNs with MobileNetV1 + SSDLiteX.
(SSDLiteX will be published soon.)
These models are pruned and implemented on a low-end FPGA
with only on-chip memory, without DRAM.
The implementation details will be presented in a poster session of ISFPGA 2023,
and the full version is uploaded to arXiv.

	@article{aocstream_2021,
		author = {Kang, Hyeong-Ju},
		title = {AoCStream: All-on-Chip CNN Accelerator With Stream-Based Line-Buffer Architecture},
		version = {1},
		date = {2011-12-19},
		eprinttype = {arxiv},
		eprintclass = {cs.LG, cs.GT},
		eprint = {http://arxiv.org/abs/1112.4344v1},
		url = {http://arxiv.org/abs/1112.4344v1}
	}
	@inproceedings{aocstream_isfpga,
		author = {Kang, Hyeong-Ju},
		title = {AoCStream: All-on-Chip CNN Accelerator With Stream-Based Line-Buffer Architecture},
		booktitle = {Proceedings of ACM/SIGDA International Symposium on Field Programmable Gate Arrays},
		year = {2023},
		pages = {}
	}

| CNNs						| Input Size	| prototxt	| unpruned AP50, AP\*	| pruned (p/g=6/8) AP50, AP\*	|
|---------------------------|---------------|-----------|-----------------------|-------------------------------|
| MobileNetV1 + SSDLiteX	| 320			| [prototxt]| [35.0%, 21.9%](https://drive.google.com/file/d/1aWww9mvZRwQmguftiiHuhGAGF0ezzjaa/view?usp=share_link) | [34.5%, ](https://drive.google.com/file/d/1e41BB2OrMypdDw6P_1JHu0lWaiAWjj9J/view?usp=share_link) |
| MobileNetV1 + SSDLiteX	| 384			| [prototxt]| [37.6%, 23.8%](https://drive.google.com/file/d/1dkMhDVTCjnNQ4k0PGqBzaez6EksjBfqp/view?usp=share_link) | [37.1%, ](https://drive.google.com/file/d/178zxWFNIX7tYtmQY3rnltha96HHkjlW3/view?usp=share_link) |
| MobileNetV1 + SSDLiteX	| 484			| [prototxt]| [41.1%, 25.7%](https://drive.google.com/file/d/1x0waumEgV2GEjCthoIw3cRMFJ3c2i8ZN/view?usp=share_link) | [40.4%, ](https://drive.google.com/file/d/1dqC-uDl15HbmGV8Fz9NHPRkn9_fvhA4O/view?usp=share_link) |
| MobileNetV1 + SSDLiteX	| 512			| [prototxt]| [42.1%, 26.6%](https://drive.google.com/file/d/1QR7LwgC5bYs6Fac7wN3Die-DGo0bmjQ1/view?usp=share_link) | [40.1%, ](https://drive.google.com/file/d/11ufSHoQivGDTEMzhj5z4crkRyAnNpCjn/view?usp=share_link) |


\* AP: MS COCO AP

