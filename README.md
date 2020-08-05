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
