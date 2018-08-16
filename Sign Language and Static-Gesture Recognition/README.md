# Sign Language and Static-Gesture Recognition

Gesture recognition is an open problem in the area of machine vision, a field of computer science that enables systems to emulate human vision. Gesture recognition has many applications in improving human-computer interaction, and one of them is in the field of Sign Language Translation, wherein a video sequence of symbolic hand gestures is translated into natural language.

![Sign Language](https://github.com/Omkar-Ajnadkar/Neural-Network-Projects/blob/master/Sign%20Language%20and%20Static-Gesture%20Recognition/dataset/2.png)

## [Blog Post](https://medium.com/@blackbird98/sign-language-and-static-gesture-recognition-eaafd6ab00a5)

## Dataset

The dataset format is patterned to match closely with the classic MNIST. Each training and test case represents a label (0-25) as a one-to-one map for each alphabetic letter A-Z (and no cases for 9=J or 25=Z because of gesture motions). The __training data__ (27,455 cases) and __test data__ (7172 cases) are approximately half the size of the standard MNIST but otherwise similar with a header row of label, pixel1, pixel2....pixel784 which represent a single 28x28 pixel image with grayscale values between 0-255. 

## Data Preprocessing

As the dataset has already given csv values for images, we don't need to do much preprocessing. If dataset of image was in raw format, we have to convert them in csv format arrays before doing any of the further operations. Still we perform following steps:

- Seperate features(784 pixel columns) and output(result label)
- Reshape the features
- One Hot Encoding on result 

## Model

We will use Keras to build the simple CNN(Convolutional Neural Network).

There are total 7 layers in the CNN:

1. 1st Convolutional Layer with `relu`
2. 1st Max Pooling 
3. 2nd Convolutional Layer with `relu`
4. 2nd Max Pooling
5. Flattening
6. First Full Layer with `relu`
7. Output Layer with `sigmoid`

## Results

- Training Set Accuracy: `96.06 %`
- Test Set Accuracy: `87.77%`


Any suggestions, always welcome! 

Send a pull request, if you see any errors...
