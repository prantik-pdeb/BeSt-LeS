# BeSt-LeS: Benchmarking Stroke Lesion Segmentation using Deep Supervision [[arxiv link]](https://arxiv.org/abs/2310.07060)
### *Accepted to MICCAI BrainLes 2023 (Oral)*

*In Progress*

## Table of Contents

- [Introduction](#introduction)
- [Results](#results)
  - [2D U-Net Architectures](#2d-u-net-architectures)
  - [3D U-Net Architectures](#3d-u-net-architectures)
  - [Visualizations of 2D Models](#visualizations-of-2d-models)
- [Pre-trained Weights](#pre-trained-weights)

## Introduction

Brain stroke poses a significant challenge to global health. Effective remedies and prevention strategies are crucial. The immediate identification of stroke and risk stratification is vital for clinicians. Automated segmentation models play a key role in assisting experts. This work benchmarks various end-to-end supervised U-Net style models using the ATLAS v2.0 dataset, focusing on 2D and 3D brain images. We achieved the highest Dice score of 0.583 with a 2D transformer-based model and 0.504 with a 3D residual U-Net. The Wilcoxon test was conducted for 3D models to correlate predicted and actual stroke volumes. For reproducibility, code and model weights are available here.

## Prerequisites

- **Python** 3.9.12
- **PyTorch** 1.12.1
- **NumPy** 1.23.5
- **Scikit-learn** 1.2.2
- **Nibabel** 5.1.0
- **SciPy** 1.10.1
- **Nilearn** 0.10.1
- **OpenCV** (cv2) 4.7.0

You can install these dependencies using pip:

```bash
pip install torch==1.12.1 numpy==1.23.5 scikit-learn==1.2.2 nibabel==5.1.0 scipy==1.10.1 nilearn==0.10.1 opencv-python==4.7.0

```
## Results

### 2D U-Net Architectures

The following table presents the performance metrics of various 2D U-Net models:

| Method                | Dice Score | IoU Score | Precision | Recall |
|-----------------------|------------|-----------|-----------|--------|
| U-Net                 | 0.417      | 0.337     | 0.580     | 0.360  |
| Residual U-Net        | 0.456      | 0.375     | 0.592     | 0.420  |
| Attention U-Net       | 0.487      | 0.396     | 0.636     | 0.439  |
| TransAttn U-Net       | 0.572      | *0.477*   | *0.660*   | 0.565  |
| U-Net Transformer     | *0.583*    | 0.475     | 0.659     | *0.591*|

### 3D U-Net Architectures

The table below illustrates the performance of various 3D U-Net models:

| Method                | Dice Score | IoU Score | Precision | Recall |
|-----------------------|------------|-----------|-----------|--------|
| U-Net                 | 0.450      | 0.350     | 0.584     | 0.444  |
| Residual U-Net        | *0.504*    | *0.393*   | *0.585*   | 0.533  |
| Attention U-Net       | 0.469      | 0.369     | 0.498     | *0.578*|

### Visualizations of 2D Models

Here are visualizations of the 2D models, organized into two sections for clarity:

#### Model Visualizations (Subject ID: sub-r004s004)

<table>
  <tr>
    <td style="text-align:center; vertical-align:middle"><strong>U-Net</strong><br><img src="docs/sub-r004s004_U-NET.gif" alt="U-Net Visualization" width="300"/></td>
    <td style="text-align:center; vertical-align:middle"><strong>Residual U-Net</strong><br><img src="docs/sub-r004s004_res-UNET.gif" alt="Residual U-Net Visualization" width="300"/></td>
    <td style="text-align:center; vertical-align:middle"><strong>Attention U-Net</strong><br><img src="docs/sub-r004s004_attention-U-NET.gif" alt="Attention U-Net Visualization" width="300"/></td>
  </tr>
  <tr>
    <td colspan="3" style="text-align:center; padding:10px;"></td>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:middle"><strong>TransAttn U-Net</strong><br><img src="docs/sub-r004s004_transattn-UNET.gif" alt="TransAttn U-Net Visualization" width="300"/></td>
    <td style="text-align:center; vertical-align:middle"><strong>U-Net Transformer</strong><br><img src="docs/sub-r004s004_U-NET-Transformer.gif" alt="U-Net Transformer Visualization" width="300"/></td>
  </tr>
</table>

#### Model Visualizations (Subject ID: sub-r027s050)

<table>
  <tr>
    <td style="text-align:center; vertical-align:middle"><strong>U-Net</strong><br><img src="docs/sub-r027s050_U-NET.gif" alt="U-Net Visualization" width="300"/></td>
    <td style="text-align:center; vertical-align:middle"><strong>Residual U-Net</strong><br><img src="docs/sub-r027s050_res-U-NET.gif" alt="Residual U-Net Visualization" width="300"/></td>
    <td style="text-align:center; vertical-align:middle"><strong>Attention U-Net</strong><br><img src="docs/sub-r027s050-attnetion-U-NET.gif" alt="Attention U-Net Visualization" width="300"/></td>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:middle"><strong>U-Net Transformer</strong><br><img src="docs/sub-r027s050-transattn-U-NET.gif" alt="U-Net Transformer Visualization" width="300"/></td>
    <td style="text-align:center; vertical-align:middle"><strong>TransAttn U-Net</strong><br><img src="docs/sub-r027s050-U-NET-Transformer.gif" alt="TransAttn U-Net Visualization" width="300"/></td>
  </tr>
</table>

## Pre-trained Weights

We provide pre-trained weights for our models to facilitate easy experimentation and evaluation. You can download the weights using the links below:

- **[U-Net](https://www.dropbox.com/scl/fi/ia0n96z3d9g8ibe1lzm6j/best_model_unet2D.pth?rlkey=wr9vdunay07n3u6qdun7dh97k&st=bqjwdonz&dl=0)**
- **[Residual U-Net](https://www.dropbox.com/scl/fi/0glgirnwpo01sc8efwmww/best_model_resunet2D.pth?rlkey=018yhm2xtum7ou0bnnu6jjmg7&st=sriitu6n&dl=0)**
- **[Attention U-Net](https://www.dropbox.com/scl/fi/2axed3aijmburefmqmqbw/best_model_att_unet2D.pth?rlkey=3gqgpayl2ot67k5qmfbch6noe&st=bgbsrpc6&dl=0)**
- **[TransAttn U-Net](https://www.dropbox.com/scl/fi/3uw3ustku74h5ozoxqq0m/best_model_transatt_unet2D.pth?rlkey=2ugr9af23e1vskqy8mr9laudz&st=0dfb8tzs&dl=0)**
- **[U-Net Transformer](https://www.dropbox.com/scl/fi/z60c0alj8pyd1u28lcjdj/best_model_trans_unet.pth?rlkey=l2rkefzbdcxzufrdkfwnl4wym&st=di3qkprq&dl=0)**




## Table of Contents

1. [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
2. [Results](#results)
3. [Contributing](#contributing)
4. [License](#license)
5. [Acknowledgments](#acknowledgments)

## Getting Started

Explain how to get started with your project. Provide step-by-step instructions for setting up the environment and running the code.

### Prerequisites
List the software, libraries, and dependencies:
Python 3.9.12

Pytorch 1.12.1

Numpy 1.23.5

Scikit-learn 1.2.2

Nibable 5.1.0

Scipy 1.10.1

Nilearn 0.10.1

cv2 4.7.0

### Installation:




## Results:

## Contributing:


## License:


## Acknowledgments:


## References:


