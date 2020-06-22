# correlate-voi
Python script to locate a volume of interest in a tomographic stack based on publication: https://doi.org/10.1016/j.ces.2020.115736

Requires scikit-image, numpy, some tomographic data to play with. 

This script uses fast normalised cross correlation to locate a volume of interest in a stack of in-situ tomographic images where 
volumes of interest (groups of particles) shift unpredictably. This has been tested in the publication listed above on a fluid 
suspension captured at the APS 2-BM beamline. See the jupyter notebook.
