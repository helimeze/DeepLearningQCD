# Complex Wilson Loop - quark anti-quark potential project

Machine learning project to use network setup to learn the deformation parameters in our deformed AdS-BH model metric. 

## Setup

1. Create virtual environment: 
```bash
python3 -m venv .venv
source .venv/bin/activate
````

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Problem setup

We have lattice data for QCD potential for different temperatures. We want to find the metric functions just from the potential data, without any information about the background itself. One solution to this inverse problem is to set up a network that learns the metric functions, such that the potential computed using the metric functions matches the data. This project has additional complexity due to the data being partially complex: The potential has real branch and complex branch, so that when we allow the holographic coordinate to have complex values, we have linear tail for the potential as afunction of separation, instead of it breaking and creating swallowtail shape. This allows us to 1) probe the physics at larger separations, and 2) Construct metric just from lattice data, and compare it to existing models such as IHQCD.

The model we use is deformed AdS-BH, so that we learn deformation parameters `a(z)` and `b(z)` that are polynomials. For the non-deformed, baseline case of pure AdS-BH, we have simply $a=b=0$. The metric functions are

$$ f(z) = \frac{e^{a(z)}}{1-z^4/z_h^4} $$

## Data

Data files should be placed in the `data/`directory (our data is not public so it will not display here in the repository)

## Modules 

- `dataset_HR.py`- Module for dataset handling
- `constants.py`- Module for the dtype constants
- `model_HR_new.py`- Module for the model


## Usage

Main training notebook: `training.py`

