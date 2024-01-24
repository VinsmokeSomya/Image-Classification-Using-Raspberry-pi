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

## Download the example files

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

## Run the example

```
python3 classify.py
```
*   You can optionally specify the `model` parameter to set the TensorFlow Lite
    model to be used:
    *   The default value is `efficientnet_lite0.tflite`
    *   TensorFlow Lite image classification models **with metadatafrom**
    (including models from [TensorFlow Hub](https://tfhub.dev/tensorflow/collections/lite/task-library/image-classifier/1)
    or models trained with TensorFlow Lite Model Maker are supported.)
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

## Speed up the inferencing time (optional)

If you want to significantly speed up the inference time, you can attach an
ML accelerator such as the [Coral USB Accelerator](
https://coral.withgoogle.com/products/accelerator)—a USB accessory that adds
the [Edge TPU ML accelerator](https://coral.withgoogle.com/docs/edgetpu/faq/)
to any Linux-based system.

If you have a Coral USB Accelerator, you can run the sample with it enabled:

1.  First, be sure you have completed the [USB Accelerator setup instructions](
    https://coral.withgoogle.com/docs/accelerator/get-started/).

2.  Run the image classification script using the Edge TPU TFLite model and
    enable the Edge TPU option.

```
python3 classify.py \
  --model efficientnet_lite0_edgetpu.tflite \
  --enableEdgeTPU
```

You should see significantly faster inference speeds.

For more information about creating and running TensorFlow Lite models with
Coral devices, read [TensorFlow models on the Edge TPU](
https://coral.withgoogle.com/docs/edgetpu/models-intro/).

For more information about executing inferences with TensorFlow Lite, read
[TensorFlow Lite inference](https://www.tensorflow.org/lite/guide/inference).
