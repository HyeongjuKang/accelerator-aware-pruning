# accelerator-aware-pruning

[![License](https://img.shields.io/badge/license-BSD-blue.svg)](LICENSE)

By [Hyeong-Ju Kang](http://)

### Introduction

Accelerator-aware pruning(AAP) is a pruning scheme that considers an acceleartor
	structure.
With accelerator-aware pruning, you can imporove the operator utilization
	of the sparse NN accelerators like Cambricon-X and EIE,
	and can design a sparse NN accelerator with much lower complexity.
For more details, please refer to my [arXiv paper](http://arxiv.org/abs/1804.09862)
	or [the version](https://ieeexplore.ieee.org/document/8693518) published in IEEE Transactions on
	Circuits and Systems for Video Technology.

### Citing AAP

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

### Pruned Models

#### Classification CNNs
##### Convolutional layers pruned
| CNNs		| g	| p	| top-5 accuracy	| pruned models |
|-------	|---|---|------------------:|--------|
| AlexNet\*	| 8	| 6	| 80.42%			|[caffemodel](https://drive.google.com/file/d/1EXLi9WwaU-9qQhLL1hSBGF7qP7jl58Dt/view?usp=sharing) 
| VGG 16	| 8	| 6	| 89.91%			|[caffemodel](https://drive.google.com/file/d/117o2CGn4AAeG75DwvPF1NScFYCRUriOY/view?usp=sharing)|
| ResNet-50	| 8	| 6	| 91.14%			|[caffemodel](https://drive.google.com/file/d/1mke-oqIrlHMSwJ0GicKHMWDKnfWYbz7g/view?usp=sharing)
| ResNet-152| 8	| 6	| 92.33%			|[caffemodel](https://drive.google.com/file/d/13w-tXk8kvxlZhQSieGfAettYDXnYNo60/view?usp=sharing)

* No LRN was used in [AlexNet](https://drive.google.com/file/d/1EytqXiBdhqm1coD6jmyDeY6qr6xp5NoP/view?usp=sharing).
https://drive.google.com/drive/folders/18CeiPEtS6AI9vQmXGiyfi39mm9J_m2Bk?usp=sharing

The pruned models will be uploaded here in a month.
