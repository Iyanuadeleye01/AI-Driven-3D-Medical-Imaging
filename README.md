# Lung Segmentation from Chest X-ray using U-Net
This project demonstrates the use of a U-Net convolutional neural network for semantic segmentation of lung fields in chest X-ray (CXR) images. It uses labelled 2D X-ray images to train the model to extract lung regions. Additionally, the project includes image preprocessing and cleaning of a separate 2D dataset using OpenCV, although this secondary dataset was not used to train any models.

# Project Structure
lung-segmentation-from-chest-x-ray.ipynb: Main notebook for training and evaluating the U-Net model on labelled X-ray images.

3D_image.ipynb: Notebook for cleaning and visualising a separate 2D image dataset using OpenCV (not used for model training).

ClinicalReadings/: Contains documentation related to the CXR datasets.

NLM-MontgomeryCXRSet-ReadMe.pdf

NLM-ChinaCXRSet-ReadMe.docx

CXR_png/: Directory with original CXR images.

masks/: Directory with corresponding segmentation masks (566 modified masks).

test/: Test data for model evaluation.

3D_Object_Recognition_Data/: Secondary image dataset (cleaned only).

images/

annotations/

metadata.csv

 # Model Summary
Model: U-Net for semantic segmentation

Input: 2D X-ray images resized to 256x256

Output: Binary lung mask per image

Total Labelled Samples: 566 X-ray images with corresponding masks

Training Metrics:

Dice Coefficient: High overlap between predicted and ground truth masks

IoU Score: Demonstrated strong segmentation accuracy

Speed:

Mask preprocessing and training sample generation:

566/566 [01:35<00:00, 5.93it/s]

566/566 [01:29<00:00, 6.31it/s]

# Dataset
Primary Dataset
Name: Lung Segmentation

Content: 2D X-ray images with annotated lung masks

Sources: NIH, Montgomery & China CXR sets

Secondary Dataset (Exploratory Use Only)
Name: 3D_Object_Recognition_Data

Content: 1613 images (1492x3 resolution)

Usage: Cleaned using OpenCV (resizing, grayscale conversion, Otsu thresholding, and segmentation)

Note: Not used for model training

 Data Cleaning (Secondary Dataset)
Performed in 3D_image.ipynb using OpenCV:

Resizing images to 256x256

Grayscale conversion

Gaussian denoising

Otsu's thresholding for mask generation

Mask inversion (if background is white)

Bitwise masking for visual segmentation

Visualisation was done for the first few images to inspect the cleaning result.

# Visual Outputs
The project includes visualisations:

Input X-ray

Ground truth mask

Predicted mask

Overlap visual

Cleaned segmented results from OpenCV

# Tools & Libraries
Python 3.10+

TensorFlow / Keras

OpenCV

NumPy, Matplotlib

Google Colab (GPU runtime)

# How to Use
Clone the repository or upload .ipynb files to Google Colab.

Upload and extract the dataset into the/content directory.

Run lung-segmentation-from-chest-x-ray.ipynb to train and evaluate the U-Net model.

Run 3D_image.ipynb to explore and clean the additional dataset.

# Limitations
The secondary dataset was cleaned but not used for training due to a lack of masks.

The project focused solely on 2D segmentation, not 3D volume reconstruction.

 # Acknowledgements
NIH Chest X-ray datasets (Montgomery & China)

OpenCV for powerful image preprocessing

Google Colab for providing free GPU support



