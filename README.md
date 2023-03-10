# Project 2 Machine learning 

Hi teachers, we want to emphasize that we only have 2 group members to complete project 2 but we tried our best, because one of my earlier teammate dropped this course.

**The README outlines the requirements, project structure and the way to reproduce our final results. For more details regarding on our project and its implementation, check the paper and the source code.**

## Authors:
- Rongchen Wang
- Jin Yan


## Abstract:



## Required packages
Apart from the basic packages, the project is done under:  
- Image==1.5.33  
- matplotlib==3.3.4  
- numpy==1.20.1  
- skimage==0.0  
- torch==1.10.0  
- torchvision==0.11.1


You can install the required packages by `pip install -r required_packages.txt` or `conda install required_packages.txt`
 
## Important: Instructions for run.py

You can get the required files which are needed for the reproduction of our submission from this repository. Please do not forget to create the folder hierarchy if you manually download the model and the dataset. Specifically, your architecture of the project should look like this:

```
.
├──test_set_images                                        # Testing Images with no groundtruth
├──training                                               # Training dataset and its groundtruth
|   ├───groundtruth
|   └───images
├── result                                                # Model output results
|   ├── RR_Unet0.0007submission.csv                       # The best submission on AICrowd
|   ├── RR_Unet0.0007.pkl                                 # The best model parameters
|   ├── RR_Unet0.0007_performance.pkl                     # The best model performance, like loss and F1-score
|   ├── RR_Unet0.0007train_loss.png                       # The picture of train loss, train F1-score, valid loss and valid F1-score
|   └── new_images                                        # The test images overlayed with predicted road
├── data_process.py                                       # To enlarge dataset using data augmentation
├── mask_to_submission.py                                 # Functions converting the model output to csv format
├── metrics.py                                            # Several loss functions 
├── run.py                                                # To reproduce our best results or train a new model
├── model.py                                              # Class of models we built
├── required_packages.txt			                              # Required packages
├── functions.py			                                       # Functions to compute f1
├── google colab.ipynb                                    # Use google colab to run our code
├── ML_project_2.pdf                                      # This is our experiment report
└── README.md
```
The best result we get in AICROWD is RR_Unet with 0.0007 learning rate and batch size 6.  

When you run new models, the new images will be overwritten and generate new 4 documents:  
submission.csv;  
model+learningrate.pkl;  
model+learningrate_performance.pkl;  
model+learningratetrain_loss.png

## Results

|Model   |   Learning rate |    F1-score   |   Accuracy|
| :-----:| :----: | :----: |:----: |
|U_Net    |  0.0003   |         0.874  |       0.932|
|Res_Unet |  0.0003   |         0.884   |      0.939|
|RR_Unet  |  0.0003   |         0.882   |      0.937|
|Attention_Res_Unet| 0.0003  |  0.882     |    0.938|
|U_Net   |   0.0004  |          0.870  |       0.930|
|Res_Unet   |0.0004          |  0.878    |     0.936|
|RR_Unet |   0.0004  |          0.878   |      0.937|
|Attention_Res_Unet | 0.0004 |  0.877   |      0.937|
|U_Net   |   0.0005  |          0.868   |      0.930|
|Res_Unet|   0.0005  |          0.875   |      0.934|
|RR_Unet|    0.0005  |          0.884   |     0.938 |
|Attention_Res_Unet|  0.0005  |  0.874	 |      0.934|
|U_Net |     0.0007|            0.865	|       0.928|
|Res_Unet|   0.0007  |          0.885	|       0.938|
|**RR_Unet** |   **0.0007**   |         **0.885**	 |      **0.940** |
|Attention_Res_Unet|  0.0007 |  0.880	 |      0.937|
     
## How to run
We used Google Colab, which provides a free GPU to run our model. It is also possible to run our model with CPU, but it would be time-consuming.   
To reproduce our final results, note to change the path name where documents is located!
- You can run this project by using following command:
```
!python run.py
```
Both of the training and testing are porformed on Google Colab GPU(12G). 

