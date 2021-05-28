# crystallography
toolbox for orientation data

# Fork to compute IPF color for HCP crystals

## Installation instructions

This was tested on python 3.6.9

```
virtualenv -p python3.6 py3
source py3/bin/activate
pip install -r requirements.txt
cmake .
cmake --build .
make install
```

## Usage

```
import crystallography as cr

# let X be some array of quat vectors
X = np.load('quat_file.npy')

# compute IPF colors
ipf_colors = cr.ipf_color_hcp(X)
```

## Important notes

* The quaternion dimension is assumed to be the last axis of the array
* The quat must be in scalar first format, which is different than Dream3d's default of scalar last
* The returned RGB channels will be floats from 0-1

