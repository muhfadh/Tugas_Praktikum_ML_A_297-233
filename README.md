# ⚡️ Acral Melanoma Detection ⚡️

**Paper Rujukan :** [Acral melanoma detection using dermoscopic images and convolutional neural networks](https://vciba.springeropen.com/articles/10.1186/s42492-021-00091-z)

## Overview Jurnal
Project ini adalah untuk mendeteksi Acral Melanoma (*Skin Cancer in hand and foot*) dengan *Dermoscopic Images*.

***Link Dataset yang digunakan :*** [Acral melanoma and benign data set](https://figshare.com/s/a8c22c09f999f60a81bd).
Preprocessing yang digunakan : Artifacts Removal, Cropping, Resizing, Enhancement, Augmentation

Model yang digunakan : Deep ConvNet dengan 7 Layer seperti gambar di bawah ini
![image](https://user-images.githubusercontent.com/43193982/143890978-aefc1ad2-59af-4a6f-91fb-abe1adf28702.png)

Selain itu, jurnal tersebut juga menambahkan dengan  pre-train model AlexNet dan ResNet

AlexNet :

![image](https://user-images.githubusercontent.com/43193982/143892198-e9530895-014c-47ec-a167-87bcb9f89527.png)


ResNet :

![image](https://user-images.githubusercontent.com/43193982/143892263-9252e3bc-3755-4645-a217-3e06efb24294.png)


**Akurasi** yang didapatkan pada jurnal tersebut dengan model Deep ConvNet adalah : **91.03%**

Sedangkan dengan tambahan pretrain AlexNet dan Resnet adalah : **95.87%** dan **97.47%**


## Overview Dataset 
***Link Dataset yang digunakan :*** [Acral melanoma and benign data set](https://figshare.com/s/a8c22c09f999f60a81bd).
Gambar yang digunakan adalah Dermoscopic Images dengan total gambar 724 gambar. Terdiri dari 350 gambar Acral Melanoma dan 374 gambar benign nevi

Splitting Dataset : Training = 70%, Validation = 20%, Testing = 10%


## Preprocessing dan Modelling

- **Preprocessing Model 1 & 2** : resize(224,224), rotation_range=15, horizontal_flip=True, shear_range = 0.2, brightness_range = (0.2,1.0), zoom_range = 0.2, fill_mode = 'nearest'.
- Modelling Model 1 :

  summary Model 1 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143894817-4f463136-68d7-408d-acb4-ddfbd07c51e5.png)
  
  
  Graph Loss dan Accuracy Model 1 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143895098-26a9285b-5108-4e4b-a9bd-51a94aba0cc4.png)
  ![image](https://user-images.githubusercontent.com/43193982/143895152-53aff385-fb8a-4341-b27f-adc945a40085.png)

- Modelling Model 2 :

  summary Model 2 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143895372-d985df70-700f-41f0-81c5-4395cc7d5c84.png)
  
  
  Graph Loss dan Accuracy Model 2 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143895447-b1a0aeb9-1a23-4d51-bd0d-46b58b149819.png)
  ![image](https://user-images.githubusercontent.com/43193982/143895503-4c8a3f07-6e12-4914-8be4-388c58d45c86.png)




- **Preprocessing Model 3, 4, & 5** : Splitting data di sini menggunakan train 80%, validation 19% dan testing 1%
  > resize(224,224), rotation_range=15, horizontal_flip=True, shear_range = 0.2, brightness_range = (0.2,1.0), zoom_range = 0.2, fill_mode = 'nearest', cropping, remove outer circle, place in square.

- Modelling Model 3 :
  
  summary Model 3 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143897330-7e690722-1a31-44d8-9d23-d4afe6a72153.png)
  
  
  Graph Loss dan Accuracy Model 3 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143897394-c2f78d9d-b9e4-4caa-9272-28e9c5bc7f30.png)
  ![image](https://user-images.githubusercontent.com/43193982/143897430-144d917c-6cf5-4837-9690-a0a417b4b6f5.png)

  Evaluation Matrix Model 3 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143897843-9b164024-e48c-4809-bec0-b986dd9c05a1.png)


- Modelling Model 4 :
  
  summary Model 4 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143898134-30ae2af9-b1e4-4a33-8c23-cb5b6baf3387.png)
  
  
  Graph Loss dan Accuracy Model 4 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143898658-52b20a0d-3503-433b-b92f-8f8162a12e3a.png)


  Evaluation Matrix Model 4 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143899074-9164b2eb-9324-4b1f-9844-aebb71dc6d2b.png)


- Modelling Model 5 :
  
  summary Model 5 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143899514-809b759b-aee5-4196-884b-a3b7beedcc8c.png)
  
  
  Graph Loss dan Accuracy Model 5 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143899656-38de1ac7-fe5b-430b-8662-99d08e4a2c80.png)


  Evaluation Matrix Model 5 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143899783-e5051c8d-d12e-4313-b5b7-dd128f26d85a.png)
 

- **Preprocessing Model 6  & 7 dengan HyperParameter Tuning** : rotation_range=15, horizontal_flip=True,shear_range = 0.2, zoom_range = 0.2, width_shift_range=0.1, height_shift_range=0.1

- Modelling Model 6 : {'num_units': 64, 'dropout': 0.2, 'optimizer': 'sgd'}

  Summary Model 6
  
  ![image](https://user-images.githubusercontent.com/43193982/143978324-0a831980-baa5-4a07-b310-2d612505e2d8.png)
  
  
  Graph Loss dan Accuracy Model 6 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143978373-eb6195b8-23f0-4f63-ab37-f4f2a71e2b04.png)


  Evaluation Matrix Model 6 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143978396-78bb326a-905a-4297-a69b-64f9ffa13a84.png)


- Modelling Model 7 : {'num_units': 256, 'dropout': 0.1, 'optimizer': 'adam'} 

  Summary Model 7
  
  ![image](https://user-images.githubusercontent.com/43193982/143978630-99a26210-6b87-48ef-97cf-6441a5e2571e.png)
  
  
  Graph Loss dan Accuracy Model 7 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143978678-bb0019aa-d064-410d-89de-cb23e9fb207e.png)


  Evaluation Matrix Model 7 :
  
  ![image](https://user-images.githubusercontent.com/43193982/143978708-aedf4c56-59ba-4fcc-91a7-c295fb338395.png)
  
 - Modelling dengan Pretrained Model VGG19 :
   
   Summary Model :
   
   ![image](https://user-images.githubusercontent.com/43193982/145917341-385f4747-abf1-485a-a302-0924213c8ac4.png)


   Graph Loss dan Accuracy Model :
   
   ![image](https://user-images.githubusercontent.com/43193982/145917426-465f0fce-dbba-401d-8c67-37bb321b83a8.png)

    
   Evaluation Matrix Model :
   
   ![image](https://user-images.githubusercontent.com/43193982/145917549-d1ce8e48-59a8-460b-a5c5-42e342726398.png)

   


 - Modelling dengan Pretrained DenseNet201 :
 - 
   Summary Model :
   
   (Summary terlalu panjang sehingga hanya bagian FC saja)
   
   ![image](https://user-images.githubusercontent.com/43193982/145918013-d8d264b6-1d3f-422b-870a-8126882610be.png)


   Graph Loss dan Accuracy Model :
   
   ![image](https://user-images.githubusercontent.com/43193982/145918051-d52e61b9-d360-4cab-a38a-215d94167da1.png)

    
   Evaluation Matrix Model :
   
   ![image](https://user-images.githubusercontent.com/43193982/145918122-e2e6f36f-a5d2-4f21-b625-9221e1716661.png)


## Predict Data

- Predict Data dengan Model 6 :

![image](https://user-images.githubusercontent.com/43193982/143978948-78986fe3-b210-405e-846a-1c4fb4aedb1a.png)


- Predict Data dengan Model 7 :

![image](https://user-images.githubusercontent.com/43193982/143979024-e5c37150-1d01-41e7-b9e0-812dd8fb6a14.png)

- Predict dengan 2 Model Pretrained VGG19 dan DenseNet201 :

![image](https://user-images.githubusercontent.com/43193982/145918349-5f324a40-8b5e-4f7d-817a-b4f59bcb42ab.png)

## Local Development

![image](https://user-images.githubusercontent.com/43193982/147548558-9a85d443-3660-46b2-850f-3cad2ce36675.png)


![image](https://user-images.githubusercontent.com/43193982/147548595-9739cda3-44ee-4ab3-abd5-b6c60f3acaac.png)


## 👩‍💻👩‍💻 Authors

- [@muhfadh](https://www.github.com/muhfadh)
- [@Naufal-FTech](https://github.com/Naufal-FTech)

<a href="https://github.com/anuraghazra/github-readme-stats/actions">
  <img alt="Language Python" src="https://img.shields.io/badge/Language-Python-blue" />
</a>



