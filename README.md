## INTRODUCTION
* The resporatory is a 3D image segmentation project that started with images and masks at http://medicalsegmentation.com/covid19/. Then those images and masks were found to be corrupted while slicing. Therefore, images and infection masks at https://zenodo.org/record/3757476#.YIa6cJAzbIV were used and found well annotated.
* All the codes of using a 2DUNET model to train volumetric medical images through slicing are explained below in order.
## THE CODES
### 3d_image_segmentation.ipynb :
1. The code is a project for the subject called 'Image Processing' taken at Izmir Democracy University, Electrical and Eelctronics Department.
2. The code is for 3D-CT image segmentation task, training a model through slicing 3D images in X and Y directions and applying 2D-UNET model on the resulting slices. Number of slices is 10240
3. Images and maskes are obtained from http://medicalsegmentation.com/covid19/, Segmentation dataset nr. 2 (13th April). To build the model on a smaller dataset firstly, only the first image and the first mask were used for training, the rest, 8 in each category, were discarded.
4. Validation of the model is to be done later on CT images.
5. The code is considered in two stages:                                                                                                                            
   a . The first stage is slicing the image and the mask and saving it. The paths in the code are refering to my Google Drive.                                     
   b . The second stage is training on the resulting slices using the 2D-UNET model. The paths of the slices in the second stage were adjusted efore starting this stage. The paths can be checked and edited in the code.                                                  
6. The image used during training can be found in this resporatory under data/volume/1.nii.gz and has to be exctracted first. On the other hand, the mask used for the training, which is the mask for the same image, can be found in this resporatory under data/volume/mask/1.nii.gz. (The paths in the code are different and don't refere to my github).


### 3d_image_segmentation_on_10240_slices.ipynb :
* The same algorith as the '3d_image_segmentation.ipynb', However, training batch size is different between the two codes.
On the other hand the '3d_image_segmentation_on_10240_slices.ipynb' code indicates training the 2D UNet model on bigger dataset. The dataset consists of 10 training CT images and 10 COVID-19 'infection masks'. The 10 CT scans are from the Coronacases Initiative that can be freely downloaded from https://zenodo.org/record/3757476#.YIa6cJAzbIV.

* The images in this code are kept in iin.gz format while working with the code, as this types of files are way smaller in size comparing to .iin.

### 3d_image_segmentation_on_10240_slices_1epoch.ipynb
The model showed great accuracy performance and was trained on one epoch in this code and then saved for testing purposes.

### 3d_image_segmentation_Train_and_test_1_epoch.ipynb
The model is trained on 16 images and masks and test on the other four. The model of 64 batch siz and epoch step are number of train / test devided by the batch size of the train / test. The model ran on one training epoch. The slicing of images and masks were in all X, Y, and Z directions from here onwards. The quantitative test of the model shows that the model have not yet learned to detect the masks at all. The model had difficulty to be trained on google colab as it was computationally expensive to run more epochs.

### 3d_image_segmentation_Train_and_test_batch64_2epochs.ipynb
The model is then trained on 64 batch sizes but epoch steps were different; train epoch step = (number of trained data devided by the train batch size) / 2. The same went for the test epoch step. Model was trained for two epochs. Quantitative test results through IoU showed slight improvement.

### 3d_image_segmentation_Train_and_test_batch64_2then2epochs_ckpt2.ipynb
The previous model continues to be trained on extra 2 epoches. New trained model was called model_ckpt2. The quantifying testing results show more improvement.

### 3d_image_segmentation_Train_and_test_batch64_2then2then2then2epochs.ipynb
The same model continued to be trained on 8 epochs in total. Model saved is 'model_ckpt4'

### 3d_image_segmentation_Train_and_test_batch64_10epochs_augmentation.ipynb
The same model continued to be trained on 8 epochs in total. Model saved is 'model_ckpt5'. Augmentation was implemented for the the last two running epochs in this model.

### 3d_image_segmentation_Train_and_test_batch64_10epochs_augmentation_IoU.ipynb
The model trained on 10 epochs was tested and IoU for lesion detection was printed out for 32 testing masks.
testing 
### 3d_image_segmentation_Train_and_test_batch64_10epochs_augmentation_IoU_lossfunction.ipynb
The model was trained to optimize the IoU/ Jaccard metrics as a loss function starting from 8 epoch of the previous models. Quantitative results during 2 epochs of training are shown. The model is trained over 10 epochs

### 3d_image_segmentation_Train_and_test_batch64_12epochs_augmentation_IoU_lossfunction.ipynb
The model trained and saved 12epochs using IoU loss function.
