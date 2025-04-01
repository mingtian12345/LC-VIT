# LC-VIT

This repository contains the code for LC-VIT. To reproduce our model, please follow the steps below:

## Reproduction Steps

1. **Extracting Three Anatomical Views cetered on the lesion mask from 3D Images**  
   - Open the `Split_3_views(1).ipynb` file in this repository and copy the code inside.  
   - Run the copied code in the Python console of the 3DSLICER software.  
   - Before executing the code, ensure you have defined the following paths and parameters:  
     - **Original File Path**: The directory where the original 3D images are stored.  
     - **Output Path**: The directory where the results will be saved.  
     - **LESION MASK**: The lesion mask file. Ensure that both the mask and the original images are stored in the same directory.

      **Note**  
       Before extracting the three anatomical views, please ensure that the 3D images have had the skull removed. This step is necessary so that the background in LC-VIT is aggregated into a single token. We used [HD-BET](https://github.com/MIC-DKFZ/HD-BET) for skull stripping.


2. **Extracting image features for the three view using [TCformer](https://github.com/zengwang430521/TCFormer)**  


