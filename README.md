# Face Tagging

<p>The project tries to clone the functionality of a Google Images Feature that automatically groups images of people.</p>


## How to run
### 1. Clone the repo
```
$ git clone https://github.com/Akashdu/Face-Tagging/edit/main/README.md
$ cd Face-Tagging
```
### 2. Setup the Facical Landmark Encoding API (Optional)
> To be able to train model on new images you would need the API to work.

You can setup it by using any of the mentioned method
#### a) Docker
```
$ docker pull gaganmanku96/facial_landmarks_api

#### b) Docker Compose
```
$ docker-compose up
```
### 3. Run the application
```
$ jupyter notebook Main.ipynb
```
## Workflow
### 1. Facial Points Extraction
A pretrained Resnet Model is used to extract 128D facial landmark points.
### 2. Apply Algorithm
KNN algorithm is used to find the similar group.
The process works in this manner.<br>
1. Train a KNN model on first image (128D landmark points).
2. Predict on rest of the images.
3. If any image falls in 0.5 of neighbourhood then they are similar faces.
4. Repeat the step until all the images are covered.
5. Display all the groups
