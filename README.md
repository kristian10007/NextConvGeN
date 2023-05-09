# Installing

- Clone from GitHub
  `git clone `

- Load submodules
  `git submodule init`
  `git submodule update`


# Code examples
- `NextConvGeN-Example.ipynb` contains an example for using NextConvGeN.

- `XConvGeN-Example.ipynb` contains an example for using XConvGeN.


# Timeline of algorithms and changes:

1. ConvGeN
  - works on minority/majority dataset
  - Discriminator is trained for each point x in minority dataset with one of two modes (gen random points selected from):
    - majority dataset
    - Neighbourhood of Nbh(x) in majority dataset

2. NextConvGeN
  - works on dataset to create synthetic data.
  - (Optional) Neighbourhood search is done on FDC prepared data during training.
  - Discriminator is trained for each point x in dataset with: gen random points out of dataset without neighbourhood of x
  - correct synthetic features according to feature type in FDC (nominal, ordinal, continuous)
  - Improved speed


3. XConvGeN
  - works on dataset to create synthetic data.
  - Improved configuration
  - Improved speed (Feature correction works now in Tensorflow mode)
  - Generator
    - Multi headed
    - Add noise at end
