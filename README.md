# ICA Language
This pipeline extracts the dimension of resting state fMRI data representative of a functional network through independent component analysis (ICA). The method uses independent component estimation, template matching and clustering of the results given a template representing target network.
In the past this has been used with a a motor template and named the resulting map "whole-brain ICA Motor Map" (wIMM). 
The method can potentially be used for other functional networks, such as language, to replace task-based mapping (ongoing study).

Please cite our preprint of the method and results in children with epilepsy and motor: Krishnamurthy et. al. medRxiv 2022 DOI: https://doi.org/10.1101/2022.02.04.22270184) 
Found at: https://www.medrxiv.org/content/10.1101/2022.02.04.22270184v1

The method has 3 steps:
1) wIMM Component Generation - Generate ICA components at varying degrees of dimension reduction.
2) wIMM Creation - In case the network of interest has been split between components, combine all representative components into final map.
3) wIMM Task Validation - Calculating hit rate of top component and first level activation maps of task fMRI data, meant to elicit the same functional network.

# Installation
Download and unzip repository. The pipeline can be run in parts, or can be run all together from the ICA_template_pipeline script. Default values have been provided, and can be changed to fit the environment in which it is being run. 

This is a Matlab pipeline.
SPM, AFNI, FSL, antsApplyTransforms, and MeanShiftCluster are required before running this pipeline and can be installed for free at the links below.
https://www.fil.ion.ucl.ac.uk/spm/software/download/
https://afni.nimh.nih.gov/download
https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslInstallation
https://sourceforge.net/projects/advants/files/
https://www.mathworks.com/matlabcentral/fileexchange/10161-mean-shift-clustering

Matlab requirements:
SPM12
MeanShiftCluster

If you are using output of fMRIprep 21.0.2 use ANTs version 2.4 to be use ANTsapplytransformers binary

We suggest preprocessing anatomical and resting state fMRI data through fMRIPrep. If planning on utilizing validation aspect of pipeline (comparison to task activation results), generate first-level activation T-map of task-fMRI data. We used SPM for this part.

The template usd for the motor mapping (wIMM) is provided, and is the precentral and post central gyri from the Human Motor Area Template (HMAT):
Mayka, M.A., Corcos, D.M., Leurgans, S.E., Vaillancourt, D.E., 2006. Three-dimensional locations and boundaries of motor and premotor cortices as defined by functional brain imaging: a meta-analysis. NeuroImage 31, 1453–74. https://doi.org/10.1016/j.neuroimage.2006.02.004
