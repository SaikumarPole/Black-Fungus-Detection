# Black-Fungus-Detection
Black fungus detection from images using deep learning algorithms


# Data Augumentation

  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/data_aug_1.png" width="50%" height="50%" > <br>
 We are augmenting all images based on the rotation range, width shift range, height shift range, shear range, zoom range, horizontal flip, channel shift range and fill mode.<br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/data_aug_2.png" width="50%" height="50%" > <br>
	For skin disease Eczema we are generating 10 different images from one image. <br>
# Data Pre processing 
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/data_pre_1.PNG" width="50%" height="50%" > <br>
  Here we are importing split folders and splitting the whole dataset into train(70%), validation(20%) and test(10%). <br>
  Rescaling each image and keeping each target image size same (i.e, 224X224 ). <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/data_pre_2.PNG" width="50%" height="50%" > <br>
  Here applying Adam optimizer with learning rate of 0.0001( very less for more effective learning) <br>

# CNN Model

# Training with Deep Learning Models
- Xception <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_xception_1.png" width="70%" height="70%" > <br>
  Here we are using model check pointing and callbacks to save the model only if there is any increase in validation accuracy which helps in getting rid of the model overfitting. <br>
  Taking total number of epochs are 15 and batch size is 128. <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_xception_2.png" width="70%" height="70%" > <br>
  We got training accuracy of 99% and validation accuracy of 90% <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_xception_3.png" width="40%" height="40%" > <br>
- DenseNet121 <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_densenet_1.png"  width="70%"  height="40%" > <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_densenet_2.png" width="40%" height="40%"  > <br>
  Here we plot graph between accuracy and total epochs. This is helpful for checking the model overfitting. <br>
  With the same dataset and with DenseNet121 model we got training accuracy of 96% and validation accuracy of 87%, this results are till 8th epoch. Then model started overfitting.<br>

- MobileNetV2  <br>
  ![image](https://user-images.githubusercontent.com/72508066/229507791-f17f707f-cee9-409f-b649-6edcbc42c4b9.png)<br>
  With the same dataset and with MobileNetV2 model we got training accuracy of 98.33% and validation accuracy of 70.9% after running all the epochs.  <br>
  ![image](https://user-images.githubusercontent.com/72508066/229507872-ea61b10e-8a06-4ad8-8526-de0801130239.png)<br>

- VGG16
  ![image](https://user-images.githubusercontent.com/72508066/229507914-0f20845f-7b39-461d-992d-b4c750a4113e.png)<br>
  With the same dataset and with VGG16 model we got training accuracy of 89.6% and validation accuracy of 81% after running all the epochs.<br>  
  ![image](https://user-images.githubusercontent.com/72508066/229508001-5917ab43-6919-4f6b-b2b2-96dcf4939e14.png)<br>
  Here we plot graph between accuracy and total epochs for VGG-16 Model. This is helpful for checking the model overfitting. It is overfitting after 7th epoch approximately. <br>
- VGG19
  ![image](https://user-images.githubusercontent.com/72508066/229508067-07bce2ba-221b-41c7-8f5f-ac2915db783d.png)<br>
  With VGG 19 model we got training accuracy of 95.48% and validation accuracy of 83.5% after running epochs upto 13. <br>
  ![image](https://user-images.githubusercontent.com/72508066/229508145-6a12c2fe-57ac-40a6-abc9-577a74a2084c.png)<br>
  Here we plot graph between accuracy and total epochs for VGG-19 Model. This is helpful for checking the model overfitting. It is overfitting after 6th epoch approximately. <br>
- Own CNN Model
![image](https://user-images.githubusercontent.com/72508066/229508254-237eb750-2cc2-4ec4-89fa-95747ab32ed2.png)
-	Sequential() is the initialization of the model. 
-	add() function adds different layers to existing model 
-	Con2D() is convolution layer which works on each and every image based on strides, padding. 
-	Dense() layer adds activation functions to the model i.e adds non-linearity to the model. 
-	summary() describes about type of layer present and its parameters. 
![image](https://user-images.githubusercontent.com/72508066/229508439-859a13fe-ac70-4e8e-a6f3-77bf14256280.png)
-	With Own model we got training accuracy of 48.9% and validation accuracy of 40.6% after running epochs upto 13.  
![image](https://user-images.githubusercontent.com/72508066/229508498-14c7305e-cce2-4e4e-8345-b88f9767b814.png)
- Here we plot graph between accuracy and total epochs for Own Model. This is helpful for checking the model overfitting. It is overfitting after 2nd epoch approximately. After 5th epoch model is not learning as we can see training and validation accuracy are same. 
# Training and Validation Accuracy Table
S.No 	Model 	Training Accuracy 	Validation Accuracy 
1 	Xception 	99% 	90% 
2 	DenseNet121 	96% 	87% 
3 	MobileNetV2 	98.3% 	70.9% 
4 	VGG 16 	89.6% 	81% 
5 	VGG 19 	95.48% 	83.57% 
6 	Own CNN Model 	48.9% 	40.6% 

# Test And Result 
- Xception
  ![image](https://user-images.githubusercontent.com/72508066/229508925-48bbd910-fc5d-4abf-bfaa-c5ff26a473ad.png)
-	After testing the data we get testing accuracy of 90.9% with steps of 32 and batch size of 128. 
- MobileNetV2
  ![image](https://user-images.githubusercontent.com/72508066/229509172-6423b426-7d4c-4277-8d20-38972cc8bd7a.png)
- After testing the data we got testing accuracy of 70.2% with steps of 32 and batch size of 128. 
![image](https://user-images.githubusercontent.com/72508066/229509283-fd00249b-704b-4cd9-ad72-ed2d88186046.png)

- VGG16
  ![image](https://user-images.githubusercontent.com/72508066/229509336-3e6d3b4b-21b7-4186-93fc-8e16199b2a0b.png)
- After testing the data we got testing accuracy of 82% with steps of 32 and batch size of 128
- VGG19
  ![image](https://user-images.githubusercontent.com/72508066/229509552-3fb9af70-4910-4a4a-a905-d96104f6a1e7.png)
- After testing the data we got testing accuracy of 83.4% with steps of 32 and batch size of 128
- Own CNN Model
  ![image](https://user-images.githubusercontent.com/72508066/229509618-12a2eca7-2609-4f32-bbf6-f246faf6f33a.png)
- After testing the data we got testing accuracy of 41.6% with steps of 32 and batch size of 128
