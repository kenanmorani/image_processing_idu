## INTRODUCTION
* The aim of this resporatory is to practise image segmentation on different datasets.
* The resporatory is a 3D image segmentation project that started with images and masks at http://medicalsegmentation.com/covid19/. Then, images and infection masks at https://zenodo.org/record/3757476#.YIa6cJAzbIV were used.
* The work includes a 2DUNET model to train slices of volumetric medical images. 
* The training happened in different stages responding to the results; i.e. trying different publicly available dataset sources and different training batch sizes. Moreover, hayperparameters were continiously checked and updated to build a better deep learning model.
## THE CODES
### 3d_image_segmentation.ipynb :
1. The code is for 3D-CT image segmentation task, training a model through slicing 3D images in X and Y directions and applying 2D-UNET model on the resulting slices. Number of slices is 10240 for each image.
2. Images and maskes are obtained from http://medicalsegmentation.com/covid19/, Segmentation dataset nr. 2 (13th April). First small data was trained, in that only the first image and the first mask were used for training a 2DUNET model. The rest of the images, 8 in each category, were discarded.
3. The code is considered in two stages; slicong the 3D images and training a 2DUNET model:                                                                                       
   a . The first stage is slicing the image and the mask and saving it. The paths in the code are refering to my Google Drive.                                     
   b . The second stage is training a 2D-UNET model. The paths of the slices in the second stage were adjusted before starting this stage.
4. The image used during training can be found in this resporatory under data/volume/1.nii.gz. They have to be exctracted first. On the other hand, the mask used for the training, which is the mask for the same image, can be found in this resporatory under data/volume/mask/1.nii.gz. 

### 3d_image_segmentation_on_10240_slices.ipynb :
* Similar to the algorithm above is applied in this code. However, training batch size is adjusted at this stage. Further more, the code'3d_image_segmentation_on_10240_slices.ipynb' code includes training the 2D UNet model on a bigger dataset. 
* The dataset consists of 10 training CT images and 10 COVID-19 'infection masks'. The 10 CT scans are from the Coronacases Initiative that can be freely downloaded from https://zenodo.org/record/3757476#.YIa6cJAzbIV.
* The images in this code are kept in iin.gz format while working with the code, as this types of files are way smaller in size comparing to .iin.

### 3d_image_segmentation_on_10240_slices_1epoch.ipynb
* The model was trained on one epoch.

### 3d_image_segmentation_Train_and_test_1_epoch.ipynb
* At this stage, the slicing of images and masks were in all X, Y, and Z directions. And this three dimentional slicing applies to all the folowwing codes.
* The same model was trained on even larger dataset. The model is trained on 16 images and masks and test on the other four. 
* Batch size is equal to 64 and the epoch step for training is number of training devided by the batch size of 64 and epoch step for tessting is the number of testing divided by the batch size of 64. 
* The model was trained over one epoch.
* The quantitative results indicate that the model have not yet learned to detect the lesion at all actually given that the number of epochs is atill just one.

### 3d_image_segmentation_Train_and_test_batch64_2epochs.ipynb
* Model was trained for two epochs. Quantitative test results, the Intersection over Union IoU, showed slight improvement.
* The model is trained on 64 batch size but epoch steps were different; train epoch step = (number of trained data devided by the train batch size) / 2. The same went for the test epoch step. 

### 3d_image_segmentation_Train_and_test_batch64_2then2epochs_ckpt2.ipynb
* The previous model continues to be trained on 2 more epoches. New trained model was called model_ckpt2. 
* The quantifying testing results showed more improvement.

### 3d_image_segmentation_Train_and_test_batch64_2then2then2then2epochs.ipynb
* The same model continued to be trained on 8 epochs in total. Model is saved under the name 'model_ckpt4'

### 3d_image_segmentation_Train_and_test_batch64_10epochs_augmentation.ipynb
* The same model continued to be trained on 8 epochs in total. 
* Model is saved under name 'model_ckpt5'. 
* At this stage augmentation of the images was implemented.

### 3d_image_segmentation_Train_and_test_batch64_10epochs_augmentation_IoU.ipynb
* The model trained on 10 epochs was tested and IoU for lesion detection was printed out for 32 testing masks.

### 3d_image_segmentation_Train_and_test_batch64_10epochs_augmentation_IoU_lossfunction.ipynb
* At this stage, the model started to be trained for optimizion of the IoU/ Jaccard metrics. The IoU matrix was made to be the loss function. 
* Quantitative results are shown. 

### 3d_image_segmentation_Train_and_test_batch64_12epochs_augmentation_IoU_lossfunction.ipynb
The model is trained and saved at this stage.

### REFERENCES:
https://github.com/madsendennis {Last Access 16.08.2021}
