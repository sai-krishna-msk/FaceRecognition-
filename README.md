
**For someone who wants to directly implement the project navigate to 04_open_face folder**

Process of facial recognition can be broken down into 3 steps

1) Face detection-: Detecting the faces out of the images and  extracting those images

2) Generating embeddings( extracting features from Faces)-:Converting the detected faces into embeddings( embeddings == features)

3) Training-: Training a model on those embeddings



## Face detection-:
When an image is given to use for recognizing faces in it , actually the image does not only contain faces in it , for that fact it does not only contain humans it has lot of
other objects in it , so it would be inefficient for to take the entire image further into the pipeline, so we extract only the faces of the people in it and send it to the next stage
There are broadly speaking two approaches haarcascade and a pretrained model (yes for even detecting faces), but as we are going to use packages we are going to explore all the different options
we have here and finding out the best on of it.

implementation-: Spoiler alert ->Fifth approach is the best (based on two metrics time and accuracy )
Note-: Codes for implementing the script's are present within the respective folders

### 1) haarcascade-: It's the most easy and classic way to implement face detection
Theory-: [Video](https://www.youtube.com/watch?v=F5rysk51txQ&t=408s)

### 2) Hog + SVM implantation-:HOG

Theory-: [Post](https://www.learnopencv.com/histogram-of-oriented-gradients/)


### 3) Using CNN face detect model in open dlib
[Post](https://www.pyimagesearch.com/2017/04/03/facial-landmarks-dlib-opencv-python/)

### 4) Using  model trained on tensorflow architecture and implementing it in opencv


### 5) Using resent

Sorce-: [Post](https://www.pyimagesearch.com/2018/02/26/face-detection-with-opencv-and-deep-learning/)

## Face embeddings and recognition-:

### 1) LBPH-:
Though LBPH is not the best method to produce embeddings for accurate face embeddings, since it also one of the ways which i have tried i am showing it.

Theory-: [Post](https://www.learnopencv.com/histogram-of-oriented-gradients/)


### 2) Open face-:
 We will be producing embeddings(features) out of the images so that we can train the model to further predict

Source-:
[Post](https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/)

Note-:
First I decided to train a standard CNN model on faces ( as we would do for object detection) It was a disaster as ( you might have guessed) because (obviously) Different faces are (very) similar to each other  than different objects , which makes it difficult for the model to mathematically encapsulate the relationship between the labels and  their features and differentiate between different faces , so this means we need better set of features( which convolution layers generate) for the model(fully connected network) to train , rather than features generated by a Regular CNN, so that is why we use a pretrained network which is specially designed to give us embeddings of the face,
I tried to code it myself, due to performance issues I ended up taking the help of Adrian's post


### Training the model-:
I have used svm to train the model of the embeddings, in open face implementation

### Face recognition summary -:
Trying many different, methods(learning many implementations) I ended up with using implementation from
[Post](https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/)
You can go to final face recognition folder in the repo to implement it (by training it to your face and testing it out)


