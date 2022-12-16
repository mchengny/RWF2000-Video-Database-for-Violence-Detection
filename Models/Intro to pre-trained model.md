## A simple intro to use the pre-trained model



#### Step 1

To preprocess the original video dataset to .npy format containing RGB and optical flow, please refer the codes [here](https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/blob/master/Preprocess/Video2Numpy.ipynb).



#### Step 2

To build the data generator for processed dataset, please refer to the codes [here](https://urldefense.com/v3/__https:/github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection/blob/master/Networks/Flow*20Gated*20Network.ipynb__;JSU!!OToaGQ!4Q1EdcJ_wHNXzz3LfNOZX64H4-wO7azcs5C1U_TM1VWDvDBvOS-guSo2NnxBnbyW7-bkGBNWQA$) .



#### Step 3

The pre-trained model is implemented by Keras, and you can load it easily by using the below codes. 

```python
from keras.models import load_model
from keras.optimizers import SGD

sgd = SGD(lr=0.01, decay=1e-6, momentum=0.9, nesterov=True)

model = load_model('./Models/keras_model.h5')

model.compile(optimizer=sgd,
              loss='categorical_crossentropy',
              metrics=['accuracy']
```

