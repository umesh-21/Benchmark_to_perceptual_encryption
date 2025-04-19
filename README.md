# Benchmark_to_perceptual_encryption

Prerequisites
Linux

Python 3

CPU or NVIDIA GPU with CUDA and cuDNN installed

Installation
Install dependencies

For pip users:

bash
Copy
Edit
pip install -r requirements.txt
For conda users:

bash
Copy
Edit
conda env create -f environment.yml
Dataset Preparation
Encrypt the dataset using AVIH:

Follow the AVIH encryption guide here:
👉 AVIH GitHub Repository

Dataset Format:

Please ensure your dataset follows the format specified in the pix2pix project:
👉 pix2pix Dataset Format Guide

Pretrained Model:

Download the ResNet pre-trained model from:
👉 ArcFace ResNet Model

Place the downloaded model file inside the ckpts folder.

Training
To train the master key model (Ga):

bash
Copy
Edit
python3 train.py --dataroot ./datasets/train_data --name facades_pix2pix --init_gain 0.01 --model pix2pix --netG resnet_9blocks --batch_size 32 --direction BtoA
Testing
To test the trained model:

bash
Copy
Edit
python3 test.py --dataroot ./datasets/test_data --name facades_pix2pix --model pix2pix --init_gain 0.01 --netG resnet_9blocks --direction BtoA
✅ Note:
Ensure your directory structure and data formats strictly follow the pix2pix specification to avoid runtime errors.
