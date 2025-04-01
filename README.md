# LC-VIT

This repository contains the code for LC-VIT. To reproduce our model, please follow the steps below:

## Reproduction Steps

1. **Extracting Three Anatomical Views cetered on the lesion mask from 3D Images**  
   - Open the `Split_3_views(1).ipynb` file in this repository and copy the code inside.  
   - Run the copied code in the Python console of the 3D Slicer software.  
   - Before executing the code, ensure you have defined the following paths and parameters:  
     - **Original File Path**: The directory where the original 3D images are stored.  
     - **Output Path**: The directory where the results will be saved.  
     - **LESION MASK**: The lesion mask file. Ensure that both the mask and the original images are stored in the same directory.

      **Note**  
       Before extracting the three anatomical views, please ensure that the 3D images have had the skull removed. This step is necessary so that the background in LC-VIT is aggregated into a single token. We used [HD-BET](https://github.com/MIC-DKFZ/HD-BET) for skull stripping.


2. **Extracting image features for the three view using [TCformer](https://github.com/zengwang430521/TCFormer)**
   - Import the TCformer model and its pretrained weights.
   - Use the three views obtained from step 1 to extract the  image features.
   - You can place the TCformer project and the `Feature_extract.ipynb` file in the same directory in VSCode.
   - Run the `Feature_extract.ipynb` file.
   - Make sure to define your input files accordingly. We store the three view inputs as follows:  
     `/../../VIT/input-2/output_slices/output_slices_DWI_BET/p0001/Red_slice.png`

     **Note**  
       You should change image_type  in ''' load_png_images''' function to extract 3 slices' features (red,green,yellow----Axial, Coronal,Sagittal)


3. **Clinical features preprocessing** 
   - Preprocessing of clinical features involves imputing missing values and encoding various categorical variables.
   - Since clinical data can differ significantly depending on the task, this part must be handled by the user according to their specific requirements.
   - We do not provide code for this step to prevent potential exposure of sensitive patient information.
   
  
4. **Multimodal Fusion**  
   - This step uses Mutual Cross Attention to fuse the clinical and image features.
   - You can follow the steps outlined in the Notebook to execute the fusion process step-by-step.
   - The Notebook also documents some of the resulting outputs for your reference.

   **Note**  
       For environment configuration, you can  refer to [TCformer](https://github.com/zengwang430521/TCFormer).
  
   




