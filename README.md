Retinal Vessel Segmentation

Overview

This project focuses on automating the segmentation of retinal blood vessels from fundus images. Accurate segmentation is essential for diagnosing and managing diseases such as diabetic retinopathy and glaucoma.

The project leverages state-of-the-art deep learning models to achieve high performance on publicly available datasets.

Features

State-of-the-art segmentation models, including U-Net and DeepLab.

Support for multiple retinal imaging datasets (e.g., DRIVE, CHASE_DB1, and STARE).

Pretrained weights for quick inference.

Tools for visualizing predictions and metrics.

Dataset

Primary Dataset

DRIVE Dataset

Description: 40 images (20 for training, 20 for testing) of the retina.

Source: DRIVE Dataset

Additional Datasets (Optional)

CHASE_DB1: Dataset Link

STARE: Dataset Link

Requirements

Ensure the following libraries and dependencies are installed:

Python >= 3.8
PyTorch >= 1.11.0
NumPy >= 1.21.0
OpenCV >= 4.5.0
Matplotlib >= 3.5.0
Scikit-learn >= 1.0.0

Install dependencies using the provided requirements.txt file:

pip install -r requirements.txt

Installation

Clone the repository:

git clone https://github.com/yourusername/retinal-vessel-segmentation.git
cd retinal-vessel-segmentation

Install dependencies:

pip install -r requirements.txt

Usage

Training

Train the model on the DRIVE dataset:

python train.py --dataset DRIVE --epochs 50

Inference

Run inference on a single image:

python predict.py --input sample_image.jpg --output segmented_image.jpg

Visualization

Visualize segmentation results:

python visualize.py --input results/segmented_image.jpg

Results

Metrics

Metric

Value

Dice Score

0.85

IoU

0.80

Sensitivity

0.88

Specificity

0.95

Visualizations

Sample Output

Original Image

Ground Truth

Predicted Segmentation







Model Architecture

This project uses the U-Net architecture for segmentation, which is widely used for biomedical image segmentation tasks.

Model Features:

Encoder-Decoder structure with skip connections.

Optimized for small datasets with data augmentation.

Project Structure

├── datasets/          # Dataset files and loaders
├── models/            # Model architecture definitions
├── scripts/           # Training and evaluation scripts
├── utils/             # Utility functions
├── results/           # Output images and metrics
├── requirements.txt   # Required dependencies
├── README.md          # Project documentation

Contribution

We welcome contributions from the community. Here’s how you can help:

Fork the repository.

Create a new branch for your feature/bugfix.

Submit a pull request with a clear description of your changes.

References

"U-Net: Convolutional Networks for Biomedical Image Segmentation" (Paper)

DRIVE Dataset: Website

PyTorch Documentation: Website

License

This project is licensed under the MIT License. See the LICENSE file for more details.
