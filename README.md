# Python script to generate README.md
readme_content = """# **Retinal Vessel Segmentation Based on Fully Convolutional Networks**

**Full paper available on** [arXiv](https://arxiv.org/abs/1911.09915)

![](Images/result_drive.png)
![](Images/result_stare.png)

**Segmentation results for DRIVE and STARE datasets:**
- (a) Retinal image
- (b) Ground truth
- (c) Output probability map
- (d) Binary segmentation

---

## **Abstract**
The morphological attributes of retinal vessels, such as length, width, tortuosity, and branching pattern and angles, play an important role in diagnosis, screening, treatment, and evaluation of various cardiovascular and ophthalmologic diseases such as **diabetes, hypertension, and arteriosclerosis**. The crucial step before extracting these morphological characteristics of retinal vessels from retinal fundus images is **vessel segmentation**.

In this work, we propose a method for retinal vessel segmentation based on **fully convolutional networks**. Thousands of patches are extracted from each retinal image and then fed into the network, with **data augmentation** applied through patch rotation. Two architectures, **U-Net** and **LadderNet**, are utilized for vessel segmentation. The performance of our method is evaluated on three public datasets: **[DRIVE](https://www.isi.uu.nl/Research/Databases/DRIVE/)**, **[STARE](http://cecas.clemson.edu/~ahoover/stare/probing/index.html)**, and **[CHASE_DB1](https://blogs.kingston.ac.uk/retinal/chasedb1/)**. Experimental results demonstrate superior performance compared to recent state-of-the-art methods.

---

## **Method**

### **Preprocessing**
- **Gray-scale conversion**
- **Standardization**
- **Contrast-limited adaptive histogram equalization (CLAHE)**
- **Gamma adjustment**

### **Patch Extraction and Data Augmentation**
- **Training Phase:**
  - 2000 patches of size **48 × 48** are randomly extracted from each image.
  - Data augmentation through rotation (90°, 180°, 270°), quadrupling the dataset to 8000 patches per image.
  - All patches (original and augmented) are shuffled and paired with their corresponding ground truth.

![](Images/input.png)

- **Testing Phase:**
  - Images are cut into patches (size 48 × 48) with a stride of **N pixels** (e.g., N = 5 or 10).
  - Each pixel is predicted multiple times, and the final result is obtained by **averaging predictions**.

### **Network Architecture**

#### **U-Net**
![](Images/U-Net.png)

#### **LadderNet**
![](Images/LadderNet.png)

---

## **Results**

### **Results on DRIVE**
**Table 1: Segmentation results of different deep learning-based methods on DRIVE. Bold values show the best score among all methods.**

| **Method**               | **F1**      | **Sn**      | **Sp**      | **Acc**     | **AUC**     |
|--------------------------|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|
| Melinscak et al. [1]     | -           | 0.7276      | 0.9785      | 0.9466      | 0.9749      |
| Li et al. [2]            | -           | 0.7569      | 0.9816      | 0.9527      | 0.9738      |
| Liskowski et al. [3]     | -           | 0.7520      | 0.9806      | 0.9515      | 0.9710      |
| Fu et al. [4]            | -           | 0.7603      | -           | 0.9523      | -           |
| Oliveira et al. [5]      | -           | **0.8039**  | 0.9804      | 0.9576      | **0.9821**  |
| M2U-Net  [6]             | 0.8091      | -           | -           | **0.9630**  | 0.9714      |
| R2U-Net [7]              | 0.8171      | 0.7792      | 0.9813      | 0.9556      | 0.9784      |
| LadderNet  [8]           | 0.8202      | 0.7856      | 0.9810      | 0.9561      | 0.9793      |
| **This work, U-Net**     | 0.8169      | 0.7728      | **0.9826**  | 0.9559      | 0.9794      |
| **This work, LadderNet** | **0.8219**  | 0.7871      | 0.9813      | 0.9566      | 0.9805      |

---

## **Running Experiments**

### **Requirements**
- **numpy** >= 1.11.1
- **PIL** >= 1.1.7
- **opencv** >= 2.4.10
- **h5py** >= 2.6.0
- **ConfigParser** >= 3.5.0b2
- **scikit-learn** >= 0.17.1

### **Training**
**Training from scratch:**
```bash
python run_training.py <configuration_drive.txt|configuration_stare.txt|configuration_chase.txt>


PyTorch Documentation: Website

License

This project is licensed under the MIT License. See the LICENSE file for more details.
