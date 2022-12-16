## RWF2000 - A Large Scale Video Database for Violence Detection



### Introduction

With the increasing of surveillance cameras in modern cities, huge amount of videos can be collected. While there are insufficient human resource for  monitoring all the screens at  one time. 

We are considering how to use techniques of video understanding to detect violent behavior so that it can give a quick alarm in time.



### File Description

- **Preprocess** contains the python script to transform original video dataset to .npy files. Each .npy file is a tensor with shape = [nb_frames, img_height, img_width, 5]. The last channel contains 3 layers for RGB components and 2 layers for optical flows (vertical and horizontal components, respectively ).

- **Networks** contain the keras implemention of our propsoed model. Also, the training scripts of single stream are provided here.

- **Models** contains the pre-trained model implemented by Keras.

  

### Dataset

- Collected raw surveillance videos from YouTube, sliced them into clips within 5s at 30 fps, and labeled each clip as Violent or Non-Violent Behavior。

- Dropped duplicated contents which appear in both training set and validation set.

- Finally we got 2000 clips and 300,000 frames as a new data set for real-world violent behavior detection under surveillance camera.

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/demo1.gif" width="400px" height="250px">
  
  

### Problems

Since all the videos are captured by surveillance cameras in public places, many of them may not have a good imaging quality due to dark environment, fast movement of object, lighting blur, etc. Here are some examples:

- Only part of the person appears in the picture

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/blocked.gif" width="400px" height="250px">

  

- Crowds and chaos

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/crowded.gif" width="400px" height="250px">

- Small object at far distance

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/far_distance.gif" width="400px" height="250px">

- Low resolution

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/low_resolution.gif" width="400px" height="250px">

- Transient action

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/transient.gif" width="400px" height="250px">



### Demo

- Example - 1

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/result_2.gif" width="800px" height="400px">



- Example - 2

  <img src="https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/raw/master/Images/result_1.gif" width="800px" height="400px">

   

### License

1. Without the approval of the SMIIP Lab, the RWF-2000 database is not allowed to be modified and redistributed.

2. Without the approval of the SMIIP Lab, RWF-2000 database is not allowed for commercial purpose.

3. In any case, the images and videos could not be used in a way that may cause damages on human’s mental health and personal privacy.

4. To use this database for publishing papers, please kindly cite the following:

   ```
   @INPROCEEDINGS{9412502,
     author={Cheng, Ming and Cai, Kunjing and Li, Ming},
     booktitle={2020 25th International Conference on Pattern Recognition (ICPR)}, 
     title={RWF-2000: An Open Large Scale Video Database for Violence Detection}, 
     year={2021},
     volume={},
     number={},
     pages={4183-4190},
     doi={10.1109/ICPR48806.2021.9412502}}
   ```




### Download

For downloading the released dataset, you have to agree with the license above by default.

- Baidu Cloud

  - link: https://pan.baidu.com/s/1bGknPlnJUtM32D8XZnUI0w 	

  - pin number: ndre

- Google Drive:
      - link: https://drive.google.com/drive/folders/1DUpRySTKNTot_eLHn8lRxhlbmGhVLL6q?usp=sharing

-  Box Drive:
  - link: https://duke.box.com/s/kfgnl5bfy7w75cngopskms8kbh5w1mvu



### Note

- Since the dataset contains 2,000 video clips extracted from about 1,000 unique videos, we have manually checked the train set and test set to avoid the data leakage between different parts. We suggest you to keep the original partition and only separate a validation set from the train set, but do not re-shuffle the entire dataset.
- The data is compressed into separate blocks. You need to decompress it by following ways:
  - Windows PC:  put all the files under the same folder, and then de-compress the first on e. All the data will be de-compressed automatically. (7Zip.exe is recommended for the compression tool)
  - Linux: concatenate the separate file blocks together, and then use unzip to decompress it.  















