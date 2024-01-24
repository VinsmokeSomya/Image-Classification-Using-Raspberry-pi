# TensorFlow Lite Python image classification example with Raspberry Pi.

## Set up your hardware
## 1) Install the TensorFlow Lite runtime

In this project, all you need from the TensorFlow Lite API is the `Interpreter`
class. So instead of installing the large `tensorflow` package, we're using the
much smaller `tflite_runtime` package.

To install this on your Raspberry Pi, follow the instructions in the
[Python quickstart](https://www.tensorflow.org/lite/guide/python#install_tensorflow_lite_for_python).

You can install the TFLite runtime using this script.

```
sh setup.sh
```

## 2) Download the example files

First, clone this Git repo onto your Raspberry Pi like this:

```
git clone https://github.com/VinsmokeSomya/Image-Classification-Using-Raspberry-pi.git 
```

Then use script to install a couple Python packages, and
download the TFLite model:

```
cd Image-Classification-Using-Raspberry-pi/image classification using raspberry pi/

# Run this script to install the required dependencies and download the TFLite models.
sh setup.sh
```

## 3) Run the example

```
python3 classify.py
```
*   You can optionally specify the `model` parameter to set the TensorFlow Lite
    model to be used:
    *   The default value is `efficientnet_lite0.tflite`
    *   TensorFlow Lite image classification models **with metadatafrom**
*   You can optionally specify the `maxResults` parameter to limit the list of
    classification results:
    *   Supported value: A positive integer.
    *   Default value: `3`.
*   Example usage:

```
python3 classify.py \
  --model efficientnet_lite0.tflite \
  --maxResults 5
```
