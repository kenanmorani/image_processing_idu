# image_processing_idu
1. The code is a project for the subject called 'Image Processing' taken at Izmir Democracy University, Electrical and Eelctronics Department.
2. The code is for 3D-CT image segmentation task, training a model through slicing 3D images in X and Y directions and applying 2D-UNET model on the resulting slices.
3. Images and maskes are obtained from http://medicalsegmentation.com/covid19/, Segmentation dataset nr. 2 (13th April). Only the first image and the first mask were used for training, the rest, 8 in each category were discarded.
4. Validation of the model is to be done later on CT images.
5. The code is considered in two stages: 
   . The first stage is slicing the image and the mask and saving it. The paths in the code are refering to my Google Drive.
   . The second stage is training on the resulting slices using the 2D-UNET model. The paths of the slices in the second stage were adjusted as in the code before starting this stage.
6. The image used during training can be found in this resporatory under data/volume/1.nii.gz and has to be exctracted first. On the other hand, the mask used for the training, which is the mask for the same image, can be found in this resporatory under data/volume/mask/1.nii.gz. (The paths in the code are different and don't refere to my github).
