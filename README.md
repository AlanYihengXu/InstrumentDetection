# InstrumentDetection

This project tells the user the instrument family of an instrument in an image using image classification.

![example](https://user-images.githubusercontent.com/107499553/180625956-9a780122-a78e-4058-a1b3-07d0d18eb674.jpg)


## The Algorithm

This project was developed using Jetson Nano. It is a retrained resnet18 model whose dataset consists of many instruments, each labelled by their instrument family's name. When it is run, it uses the imagenet.py program with the model to determine the instrument family of an inputted image.

![dataset](https://user-images.githubusercontent.com/107499553/180626075-47a7b4a8-522b-473c-9dab-530ece8a446c.jpg)


## Running this project

1. Make sure to have resnet18.onnx and labels.txt from this project downloaded on the Jetson Nano
2. Clone the jetson-inference project from GitHub using "git clone --recursive https://github.com/dusty-nv/jetson-inference" and change directories into it
3. Make sure to have python packages installed using "sudo apt-get install libpython3-dev python3-numpy"
4. Make a build directory and run "cmake ../" in the build directory
5. To classify an image, run "imagenet.py --model=$MODEL/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$LABEL/labels.txt $IMAGE $OUTPUT", where $MODEL is the folder resnet18.onnx is stored, $LABEL is the folder labels.txt is stored, $IMAGE is the image file to classify, and $OUTPUT is the name of the file to output to.
6. To see the output, scp the outputted file from the Jetson Nano onto your computer.


## Demo

[project demo](https://youtu.be/IoiPp3zwE-4)

