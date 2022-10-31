# COMPLEX ML

Physicists aim to derive a description of complex phenomena, often involving astronomical numbers of interacting electrons, atoms, molecules or other constituents in terms of only a handful of relevant quantities. In doing so they, in effect, "compress" the full description of the system into a succinct theory, providing an understanding of the phenomenon and its properties and possessing predictive power. Surprisingly, a systematic path towards that goal exists, technically known as the Renormalization Group. It is, however, very difficult to perform it in practice, especially for disordered or irregular systems, which are ubiquitous in nature. Examples include quasicrystals, cell assemblies in human brain or interactions between participants of a social network and form a part of what is collectively referred to as complex systems. Complex systems thus comprise a vast class of phenomena from atomistic and chemical scales, through biology, all the way to social interactions and properties of industrial energy networks.
As such their improved understanding is of fundamental importance and benefit to the society.

The key objective of the interdisciplinary COMPLEX ML project is to construct new analytical and computational tools helping to develop theoretical descriptions of complex systems. This is achieved by taking the suggestive "compression" metaphor seriously. 
Together with collaborators, we introduce a new approach to constructing effective theories based on the theory of data compression, originating in computer science.  The computational progress is based on close connections with developments in the field of Machine Learning (ML), which over the course of the past ten years have revolutionised many areas of engineering. In the COMPLEX ML project I use such techniques to automate certain aspects of the scientific discovery process. Conversely, I aim to improve to improve certain aspects of ML algorithms themselves, using the established connections to complex systems physics.


# RSMI-NE

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 

`rsmine` is a Python package, implemented using Tensorflow, for optimising coarse-graining rules for real-space renormalisation group by maximising real-space mutual information. 

- [Overview](#overview)
- [System requirements](#system-requirements)
- [Installation](#installation-guide)
- [Citation](#citation)

## Overview

`rsmine` employs state-of-the-art results for estimating mutual information (MI) by maximising its lower-bounds parametrised by deep neural networks [Poole et al. (2019), [arXiv:1905.06922v1](https://arxiv.org/abs/1905.06922)]. This allows it to overcome the severe limitations of the initial proposals for constructing real-space RG transformations by MI-maximization in [M. Koch-Janusz and Z. Ringel, [Nature Phys. 14, 578-582 (2018)](https://doi.org/10.1038/s41567-018-0081-4), P.M. Lenggenhager et al., [Phys.Rev. X 10, 011037 (2020)](https://journals.aps.org/prx/abstract/10.1103/PhysRevX.10.011037)], and to reconstruct the relevant operators of the theory, as detailed in the manuscripts accompanying this code [D.E. Gökmen, Z. Ringel, S.D. Huber and M. Koch-Janusz, [Phys. Rev. Lett. **127**, 240603 (2021)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.127.240603) and [Phys. Rev. E **104**, 064106 (2021)](https://journals.aps.org/pre/abstract/10.1103/PhysRevE.104.064106)].

## System requirements

### Hardware requirements

`rsmine` can be run on a standard personal computer. It has been tested on the following setup (without GPU):

+ CPU: 2.3 GHz Quad-Core Intel Core i5, Memory: 8 GB 2133 MHz LPDDR3

### Software requirements

This package has been tested on the following systems with Python 3.8.5:

+ macOS:
  + Catalina (10.15)
  + Big Sur (11.1)
  + Monterey (12.5.1)

`rsmine` mainly depends on the following Python packages:

* matplotlib
* numpy
* pandas
* scipy
* scikit-learn
* tensorflow 2.0
* tensorflow-probability

## Installation

Clone `RSMI-NE` from GitHub
```bash
git clone https://github.com/RSMI-NE/RSMI-NE
cd RSMI-NE
```
and install the `rsmine` package via `pip` in editable mode
```bash
pip install -e .
```
or create a virtual environment and install there:
```bash
./install.sh
```

## Getting started

The package can be used by importing the `rsmine` module and its submodules:
```python
import rsmine

import rsmine.coarsegrainer.build_dataset as ds
import rsmine.coarsegrainer.cg_optimisers as cg_opt
```

Jupyter notebooks demonstrating the basic usage in simple examples are provided in <https://github.com/RSMI-NE/RSMI-NE/tree/main/examples>.

## Citation

If you use RSMI-NE in your work, please cite our publications [Phys. Rev. Lett. **127**, 240603 (2021)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.127.240603) and [Phys. Rev. E **104**, 064106 (2021)](https://journals.aps.org/pre/abstract/10.1103/PhysRevE.104.064106):

```latex
@article{PhysRevLett.127.240603,
  title = {Statistical Physics through the Lens of Real-Space Mutual Information},
  author = {G\"okmen, Doruk Efe and Ringel, Zohar and Huber, Sebastian D. and Koch-Janusz, Maciej},
  journal = {Phys. Rev. Lett.},
  volume = {127},
  issue = {24},
  pages = {240603},
  numpages = {7},
  year = {2021},
  month = {Dec},
  publisher = {American Physical Society},
  doi = {10.1103/PhysRevLett.127.240603},
  url = {https://link.aps.org/doi/10.1103/PhysRevLett.127.240603}
}

@article{PhysRevE.104.064106,
  title = {Symmetries and phase diagrams with real-space mutual information neural estimation},
  author = {G\"okmen, Doruk Efe and Ringel, Zohar and Huber, Sebastian D. and Koch-Janusz, Maciej},
  journal = {Phys. Rev. E},
  volume = {104},
  issue = {6},
  pages = {064106},
  numpages = {17},
  year = {2021},
  month = {Dec},
  publisher = {American Physical Society},
  doi = {10.1103/PhysRevE.104.064106},
  url = {https://link.aps.org/doi/10.1103/PhysRevE.104.064106}
}
```
