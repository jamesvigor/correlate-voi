# Consistent Volume Segmentation
Python script to locate a volume of interest in a tomographic stack based on publication: https://doi.org/10.1016/j.ces.2020.115736

Requires scikit-image, numpy, some in-situ tomographic datasets to play with. 

This script uses fast normalised cross correlation to locate a volume of interest in a stack of in-situ tomographic images where 
volumes of interest (groups of particles) shift unpredictably, or to simply register stacks with one another in long duration in-situ analyses where you are removing your sample from an instrument and causing minor inconsistencies in the sample position. 

Code is contained within the file Stack FNCC Algorithm.ipynb

A quick outline:
----------------
We determine a template image from the first scan, then use a matrix correlation algorithm in the x,y plane in each slice which provides a correlation coefficient R in each x,y location. We then find the maximum of the interrogated slice, which gives the best match x,y point on said slice. We write this to a three dimensional numpy array containing the best match x and y location in each slice and R values for each of these maxima. Then we find the argument to the maxima of R in this array, which effectively provides the location through the depth of the stack in the z direction and provides x,y,z of the volume. See attached video.

This has been tested in the publication listed above on a fluid suspension captured at the APS 2-BM beamline. The original jupyter notebook is available as part of the publication, and the method replicated in the attached jupyter notebook.
