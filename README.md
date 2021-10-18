# x-ray-classifaction-model

## Overview
I have been tasked to build a deep neural network to train on a data set of x-ray images of pediatric patients to identify whether or not they have pneumonia. This data is sourced from Kermany et al. on Mendeley, however I personally used a version on Kaggle due to it being easier to use. The data originally consists of 5216 images in the training set, 624 in the test set, and 16 for the validation set. 

## Methods
I am going through and checking different deep neural network architectures to see which one works best with the data. I ran into the issue that I didnt have enough images in my validation set so I brought some of the test images over in order to better interpret how my models perform. I ended up with 141 images for my validation set. After choosing which architecture to use I tune it to do my best to get the highest accuracy without overfitting on the data. I then used the package lime to see what parts of the images were being used to predict whether or not a patient has pneumonia.

## Results
The model that performed the best ended up being a simple residual network. I tried to expand the res-net in order to better predict but ended up overloading my cpu and was unable to run it. I ended up only being able to generate approx. 75,000 trainable parameters compared to the 2,000,000 trainable parameters I generated with the simple res-net. With a validation accuracy of 78% the simple res-net is the best choice to predict whether or not a patient has pneumonia. 

### PreUpdated Results
![BasicConv2D_loss]('./imgs/pre_results_2_loss.png')
![BasicConv2D_acc]('./imgs/pre_results_2_acc.png')
![AlexNet_loss]('./imgs/pre_results_3_loss.png')
![AlexNet_acc]('./imgs/pre_results_3_acc.png')
![SimpleResNet_loss]('./imgs/pre_results_4_loss')
![SimpleResNet_acc]('./imgs/pre_results_4_acc')

### Updated Results
![AlexNet_loss]('./imgs/updated_results_3_loss')
![AlexNet_acc]('./imgs/updated_results_3_acc')
![SimpleResNet_loss]('./imgs/updated_results_4_loss')
![SimpleResNet_acc]('./imgs/updated_results_4_acc')
![ResNet_loss]('./imgs/results_5_loss')
![ResNet_acc]('./imgs/results_5_acc')

### Lime Results
![BasicX-ray]('./imgs/og_image_limecheck.png')
![MaskX-ray]('./imgs/mask_image_limecheck.png')
![HeatmapX-ray]('./imgs/heatmap_limecheck.png')

## Whats Next
The next step is to add regularization layers in order to combat overfitting which was found in nearly every model. Then the best idea would be to get in contact with a radiologist and go over all the lime results to make sure the model is using the correct parts of the images to predict. 

## For More Information
For a more detailed analysis of the data see my full report: [Report]('./limecheck.ipynb')

For additional information see: 
[FinalModel]('./FinalModel.ipynb')
[PreUpdated]('./MaidenVoyage.ipynb')
[Updated]('./UpdatedValidation.ipynb')


For a short presentation see:
[My Presentation]('./Presentation.pdf')
For any additional questions, please contact Ethan Helder at helderethan@gmail.com

## Repository Structure

```
    chest_xray                <- folder containing all data sets
    Img_paths
    imgs                      <- Generated from code
    limecheck.ipynb           <- Notebook with final conclusions 
    FinalModel.ipynb          
    MaidenVoyage.ipynb
    UpdateValidation.ipynb
    README.md                 <- The top-level README for reviewers of this project