# Face Recognition

## __Introduction:__  

   In the Project, we are about to perform face recognition using **openCV and Deep Learning** python.


## __Project Description__

Root directory of this project contains:
>
> - **Several folders and scripts (Contains our necessary scripts)**
> - **README.md file (Contains instructions to run the project)**

Details about the folders and files:
 >
 > - **face_detection_model(folder):** Contains necessary `face detection` models to detect faces.
 > - **dataset(folder):** Contains all the training images to train the model.
 > - **images(folder):** Contains some example images.
 > - **output(folder):** Will contain out extracted `embeddings`, `labels` and trained `recognizer`.
 > - **face_register.py:** Module to register new faces to train with.
 > - **extract_embeddings.py:** Extract embeddings from our training images.
  > - **train_model.py**: Train the recognizer with the new face embeddings.
   > - **recognize.py**: `Module` to `recognize`  faces from `given image`.
 > - **recognize_video.py**: `Module` to `recognize`  faces from `webcam video`.
 > - **nn4.small2.v1.t7**: A Torch deep learning model which produces the 128-D facial embeddings.
 > - **requirements.txt**: Contains all the dependencies of the project.

>
### __Instructions:__

> First clone the repo using the following command:  
> > `https://github.com/Apucs/face_recognition_DL.git`
> 
> Before starting we need to satisfy all the dependencies. For that reason need to execute the following command. (All the commands need to be executed from the root folder)
>
> - __Install the dependencies:__  
>> `pip install -r requirements.txt`  

> To `register` the new face, run the following command:
> 
> >`python face_register.py`  
>
> To `extract` embeddings from the new faces, run the following command:
>> `python extract_embeddings.py --dataset dataset --embeddings output/embeddings.pickle --detector face_detection_model --embedding-model nn4.small2.v1.t7`    
> 
> To `train` with the new faces, run the following command:
>> `python train_model.py --embeddings output/embeddings.pickle --recognizer output/recognizer.pickle --le output/le.pickle`  
> 
> To  start the `facial recogition` module (for single image), run the following command:
>> `python recognize.py --detector face_detection_model --embedding-model nn4.small2.v1.t7 --recognizer output/recognizer.pickle --le output/le.pickle --image images/<image_name>`
> 
> To  start the `facial recogition` module (from webcam video), run the following command:
>> `python recognize_video.py --detector face_detection_model --embedding-model nn4.small2.v1.t7 --recognizer output/recognizer.pickle --le output/le.pickle`
