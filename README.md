# Benchmark_to_perceptual_encryption

---

## Prerequisites

- Linux
- Python 3
- CPU or NVIDIA GPU with CUDA and cuDNN installed

---

## Installation

1. **Install dependencies**

   - **For `pip` users:**
     ```bash
     pip install -r requirements.txt
     ```

   - **For `conda` users:**
     ```bash
     conda env create -f environment.yml
     ```

---

## Dataset Preparation

1. **Encrypt the dataset using AVIH:**

   Follow the AVIH encryption guide here:  
   👉 [AVIH GitHub Repository](https://github.com/suzhigangssz/AVIH)

2. **Dataset Format:**

   Please ensure your dataset follows the format specified in the pix2pix project:  
   👉 [pix2pix Dataset Format Guide](https://github.com/phillipi/pix2pix)

3. **Pretrained Model:**

   Download the ResNet pre-trained model from:  
   👉 [ArcFace ResNet Model](http://ml.cs.tsinghua.edu.cn/~xiaoyang/face_models/ArcFace/model_ir_se50.pth)  

   Place the downloaded model file inside the `ckpts` folder.

---

## Training master key GAN model

To train the **master key model (`Ga`)**:

```bash
python3 train.py --dataroot ./datasets/train_data --name facades_pix2pix --init_gain 0.01 --model pix2pix --netG resnet_9blocks --batch_size 32 --direction BtoA 

```

## Testing Master key GAN model
```bash
python3 test.py --dataroot ./datasets/test_data --name facades_pix2pix --model pix2pix --init_gain 0.01 --netG resnet_9blocks --direction BtoA
```
