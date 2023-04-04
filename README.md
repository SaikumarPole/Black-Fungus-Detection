# Black-Fungus-Detection
The deep learning project aims to develop a model for detecting the black fungus disease based on images of patients. The project involves the use of a convolutional neural network (CNN) to analyze and classify medical images of patients with suspected black fungus disease.

A large dataset of medical images is collected from patients diagnosed with black fungus disease. The dataset is then pre-processed, and data augmentation techniques are applied to increase the variety and quantity of images. The pre-processed images are then used to train the CNN model.

The trained model is then tested on a separate set of images to evaluate its performance. 


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
  <img scr="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_mobile_1.png" width="40%" height="40%" /> <br>
  With the same dataset and with MobileNetV2 model we got training accuracy of 98.33% and validation accuracy of 70.9% after running all the epochs.  <br>
  <img scr="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_mobile_2.png" width="40%" height="40%" /> <br>

- VGG16 <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_vgg16_1.png" width="60%" height="60%" > <br>
  With the same dataset and with VGG16 model we got training accuracy of 89.6% and validation accuracy of 81% after running all the epochs.<br>  
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_vgg16_2.png" width="40%" height="40%" > <br>
  Here we plot graph between accuracy and total epochs for VGG-16 Model. This is helpful for checking the model overfitting. It is overfitting after 7th epoch  approximately. <br>
- VGG19 <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_vgg19_1.png" width="60%" height="60%" > <br>
  With VGG 19 model we got training accuracy of 95.48% and validation accuracy of 83.5% after running epochs upto 13. <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_vgg19_2.png" width="40%" height="40%" > <br>
  Here we plot graph between accuracy and total epochs for VGG-19 Model. This is helpful for checking the model overfitting. It is overfitting after 6th epoch approximately. <br>
- Own CNN Model <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_own_1.png" width="60%" height="60%" > <br>
  Sequential() is the initialization of the model. 
  add() function adds different layers to existing model 
  Con2D() is convolution layer which works on each and every image based on strides, padding. 
  Dense() layer adds activation functions to the model i.e adds non-linearity to the model. 
  summary() describes about type of layer present and its parameters. <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/train_own_2.png" width="40%" height="40%" > <br>
  With Own model we got training accuracy of 48.9% and validation accuracy of 40.6% after running epochs upto 13.  
  Here we plot graph between accuracy and total epochs for Own Model. This is helpful for checking the model overfitting. It is overfitting after 2nd epoch approximately. After 5th epoch model is not learning as we can see training and validation accuracy are same. 


# Test And Result 
- Xception <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/test_xception_1.png" width="60%" height="60%" > <br>
  After testing the data we get testing accuracy of 90.9% with steps of 32 and batch size of 128. 
- MobileNetV2 <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/test_mobile_1.png" width="60%" height="60%" > <br>
  After testing the data we got testing accuracy of 70.2% with steps of 32 and batch size of 128. 
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/test_mobile_2.png" width="60%" height="60%" > <br>

- VGG16 <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/test_vgg16_1.png" width="60%" height="60%" > <br>
  After testing the data we got testing accuracy of 82% with steps of 32 and batch size of 128
- VGG19 <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/test_vgg19_1.png" width="60%" height="60%" > <br>
  After testing the data we got testing accuracy of 83.4% with steps of 32 and batch size of 128
- Own CNN Model <br>
  <img src="https://github.com/SaikumarPole/Black-Fungus-Detection/blob/main/images/test_own_1.jpg" width="60%" height="60%" > <br>
  After testing the data we got testing accuracy of 41.6% with steps of 32 and batch size of 128


# Training and Validation Accuracy Table

| S.No | Model 	        | Training Accuracy 	| Validation Accuracy | 
| -----|----------------|-----------------------|-------------------- |
| 1    | Xception 	| 99% 			| 90% 		      |
| 2    | DenseNet121 	| 96% 			| 87% 		      |
| 3    | MobileNetV2 	| 98.3% 		| 70.9% 	      |
| 4    | VGG 16 	| 89.6% 		| 81% 		      |
| 5    | VGG 19 	| 95.48% 		| 83.57% 	      |
| 6    | Own CNN Model 	| 48.9% 		| 40.6% 	      |
