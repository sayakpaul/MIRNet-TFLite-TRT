# MIRNet-TFLite

This repository shows the TensorFlow Lite and TensorRT model conversion and inference processes for the **MIRNet** model as proposed by [Learning Enriched Features for Real Image Restoration and Enhancement](https://arxiv.org/pdf/2003.06792v2.pdf). This model is capable of enhancing low-light images upto a great extent. 

<p align="center">
<img src="https://github.com/soumik12345/MIRNet/raw/master/assets/lol_results.gif"</img><br>
<small><a href="https://github.com/soumik12345/MIRNet/blob/master/assets/lol_results.gif">Source</a></small>
</p>

Model training code and pre-trained weights are provided by **Soumik** through [this repository](https://github.com/soumik12345/MIRNet/). 

## Comparison between the TensorFlow Lite and original models

**TensorFlow Lite model (dynamic-range quantized)**

<p align="center">
<img src="https://i.ibb.co/MswgSSg/image.png"></img>
</p>
  
**Original model**

<p align="center">
<img src="https://i.ibb.co/LJVSG01/image.png"></img>
</p>

## About the notebooks

* `MIRNet_TFLite.ipynb`: Shows the model conversion and inference processes. Models converted in this notebook support dynamic shaped inputs.  
* `MIRNet_TFLite_Fixed_Shape.ipynb`: Shows the model conversion and inference processes. Models converted in this notebook only support fixed shaped inputs. 
* `MIRNet_TRT.ipynb`: Shows the model conversion process with TensorRT as well as the inference. Recommended if you would run inference with an NVIDIA GPU-enabled environment.
* `Add_Metadata.ipynb`: Adds [metadata](https://www.tensorflow.org/lite/convert/metadata) to TensorFlow Lite models. Metadata makes it easier for mobile developers to integrate the TensorFlow Lite models in their applications. 

## TensorFlow Lite models

* [Dynamic shape](https://github.com/sayakpaul/MIRNet-TFLite/releases/download/v0.1.0/dynamic_shape.zip) (contains dynamic-range and fp16 quantized models)
* [Fixed shape metadata-populated models on TensorFlow Hub](https://tfhub.dev/sayakpaul/lite-model/mirnet-fixed/dr/1)

## Benchmarking

<p align="center">
  <img src="https://i.ibb.co/xMF9dN8/Inference-Latency-ms.png" width=600/>
</p>

Pixel 4 was used in order to run the benchmarking tests. Also, fixed-shape TensorFlow Lite models (accepting 400x400x3 images) were only benchmarked.  

<p align="center">
  <img src="https://i.ibb.co/2PYMns5/Model-Size-MB.png" width=600/>
</p>

## Notes
If you would run inference with an NVIDIA GPU-enabled environment then please follow along with this notebook - [`MIRNet_TRT.ipynb`](https://github.com/sayakpaul/MIRNet-TFLite/blob/main/MIRNet_TRT.ipynb). If you use the TensorRT optimized model (as shown in that notebook) with an NVIDIA GPU-enabled environment the inference latency greatly improves (~0.6 seconds on a Tesla T4). [Here's a demo](https://youtu.be/BdJT3u71EDo) of running the TensorRT optimized model on a low-light video. 
 
