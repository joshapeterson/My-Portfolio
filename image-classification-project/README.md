# Detecting COVID-19 using Chest X-rays

## Overview

**Goal of Project**: Develop a deep learning model to accurately detect COVID-19 using chest x-ray images

The purpose of this project was to create a deep learning model that accurately detects COVID-19 and types of pneumonia using chest x-rays. Many of the existing models are trained on entire chest x-ray images and perform only a binary classification to detect COVID-19. In this project, we train a model on masked chest x-ray images to remove unwanted artifacts or areas of the x-ray image and perform multiclass classification to label an image as containing evidence of COVID-19 or types of pneumonia. The final developed deep learning model acheived an accuracy of 85%. Error analysis of the model indicated that most confusion arose due to the model misclassifying bacterial and viral pneumonia x-rays more often than other classes. Therefore, future work would involve improving the performance of this model on these classes. 

***Image Preparation and Selection***

The image masks were created using x and y coordinates provided for each image in the dataset. The following is an example of the masks created for the chest x-ray images:

![](images/mask.png)

The masks were then applied to each of the chest x-ray images via a bitwise and operation. The following is an example of a masked chest x-ray image:

![](images/masked_x-ray.png)

Additionally, image quality of the chest x-rays was assesed via BRISQUE scores. The following is the distribution of those scores:

<img src="images/hist.png" width="400"/>

Images with a BRISQUE score higher than Q3 of the interquartile range were removed from the dataset to minimize the effect poor quality images would have on the performance of the deep learning image classification model. 

***Model Development***

Multiple deep learning architectures for this image classification task were tested. In the end, our best performing model used the ResNet50 architecture to classify the x-ray images. 

```
class_model_base = keras.applications.ResNet50(weights="imagenet", include_top=False)
```

The ResNet50 architecture was fine-tuned for our image classification task. This was accomplished by making the weights in the last 32 layers trainable. 

```
class_model_base.trainable = True

for layer in class_model_base.layers[:-32]: # making the last 32 layers of the ResNet50 model trainable
  layer.trainable = False

print("The number of trainable weights in the pretrained model:", len(class_model_base.trainable_weights))
```

The following was the deep learning model developed using the ResNet50 architecture:

```
data_augmentation = keras.Sequential(
    [
        layers.RandomRotation(0.1, fill_mode='constant',fill_value=0),
        layers.RandomZoom(0.1),
        layers.RandomTranslation(0.1,0.1,fill_mode='constant',fill_value=0),
    ]
)

inputs = keras.Input(shape=(200, 200, 3))
x = layers.Rescaling(1./255),
x = data_augmentation(inputs)
x = keras.applications.resnet50.preprocess_input(x)
x = class_model_base(x) # using the ResNet pre-trained model as the base for my image classification model
x = layers.Flatten()(x)
x = layers.Dense(512, activation=tf.nn.relu)(x)
x = layers.Dropout(0.2)(x) # Used a dropout rate of 0.2 to regularize the model
outputs = layers.Dense(nb_classes, activation=tf.nn.softmax)(x)
model = keras.Model(inputs, outputs)

model.compile(optimizer = 'adam', 
              loss = 'sparse_categorical_crossentropy', 
              metrics = ['accuracy'])

callbacks = [
    keras.callbacks.ModelCheckpoint(
        filepath="resnet50_im_class_model.keras",
        save_best_only=True,
        monitor="val_loss")
]

history = model.fit(train_images, 
                    train_labels, 
                    batch_size=128, 
                    epochs=40, 
                    validation_split = 0.2,
                    callbacks=callbacks)
```

***Model Results***

This model acheived an accuracy of 85%. The following is a classification report from the model:

<img src="images/classification-matrix.png" width="400"/>

*Note: 0 = Bacterial Pneumonia, 1 = Healthy, 2 = Viral Pneumonia, 3 = COVID-19*

***Future Work***

When conducting an error analysis of the developed model, it was seen that the most confusion in the model arose when trying to distinguish between viral pneumonia and bacterial pneumonia. This is represented in the confusion matrix below and the lower F1-score for those classes in the classification report.  

<img src="images/confusion-matrix.png" width="500"/>

Future work would involve exploring ways to improve the performance of this model on these classes. 

## Data Source

V7 Labs. Available from: https://darwin.v7labs.com/v7-labs/covid-19-chest-x-ray-dataset/overview

## Authors

* Joshua Peterson
* Michael Gray
* Mangala Desai

## List of Primary Packages Used

numpy, pandas, tenserflow, keras, matplotlib, seaborn and imquality

## 🔗 [Link to Project Code](https://github.com/joshapeterson/My-Portfolio/blob/main/image-classification-project/image-classification-project_code.ipynb)

*[Back to Portfolio](https://github.com/joshapeterson/My-Portfolio)*
