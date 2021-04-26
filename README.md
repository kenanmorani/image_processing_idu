# 3d_image_segmentation.ipynb :
1. The code is a project for the subject called 'Image Processing' taken at Izmir Democracy University, Electrical and Eelctronics Department.
2. The code is for 3D-CT image segmentation task, training a model through slicing 3D images in X and Y directions and applying 2D-UNET model on the resulting slices. NUmber of slices is 1024.
3. Images and maskes are obtained from http://medicalsegmentation.com/covid19/, Segmentation dataset nr. 2 (13th April). Only the first image and the first mask were used for training, the rest, 8 in each category, were discarded.
4. Validation of the model is to be done later on CT images.
5. The code is considered in two stages:                                                                                                                            
   a . The first stage is slicing the image and the mask and saving it. The paths in the code are refering to my Google Drive.                                     
   b . The second stage is training on the resulting slices using the 2D-UNET model. The paths of the slices in the second stage were adjusted efore starting this stage. The paths can be checked and edited in the code.                                                  
6. The image used during training can be found in this resporatory under data/volume/1.nii.gz and has to be exctracted first. On the other hand, the mask used for the training, which is the mask for the same image, can be found in this resporatory under data/volume/mask/1.nii.gz. (The paths in the code are different and don't refere to my github).


# 3d_image_segmentation_on_10240_slices.ipynb :
* The same algorith as the '3d_image_segmentation.ipynb', However, training batch size is different between the two codes.
On the other hand the '3d_image_segmentation_on_10240_slices.ipynb' code indicates training the 2D UNet model on bigger dataset. THe dataset consists of 10 training CT images and 10 COVID-19 'infection masks'. The 10 CT scans are from the Coronacases Initiative that can be freely downloaded from https://academictorrents.com/details/136ffddd0959108becb2b3a86630bec049fcb0ff with license CC BY-NC-SA.

* The images in this code are kept in iin.gz format while working with the code, as this types of files are way smaller in size comparing to .iin.

# 3d_image_segmentation_on_10240_slices_1epoch.ipynb
The model showed great accuracy performance and was trained on one epoch in this code and then saved for testing purposes.
