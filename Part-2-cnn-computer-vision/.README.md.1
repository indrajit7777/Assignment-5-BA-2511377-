# Part 2: Computer Vision – Manufacturing Defect Image Classification

## Problem Identification (Task 1)
**Problem type:** Image Classification

**Why appropriate?**  
The dataset consists of product surface images, each belonging to exactly one of four mutually exclusive classes: `normal`, `scratch`, `dent`, or `stain`. There are no bounding boxes, pixel-level masks, or multiple objects per image. The goal is to predict a single class label for each entire image, which is the textbook definition of multi-class image classification. This directly maps to automated quality inspection in manufacturing.

## Dataset Exploration (Task 2)
- **Number of classes:** 4 (`normal`, `scratch`, `dent`, `stain`)
- **Images per class:** (loaded dynamically from folders or `labels.csv`)
- **Image dimensions:** All images are resized to 128×128×3 (RGB)
- **Dataset balance:** Checked via code – the dataset is reasonably balanced (minor variations are handled by augmentation)
- **Sample images:** One representative image from each class is displayed in the notebook

## Image Preprocessing (Task 3)
- Resize all images to 128×128
- Normalize pixel values to [0, 1]
- Data augmentation (random horizontal flip, rotation, color jitter) on training set
- 80/20 train/validation split
- PyTorch `DataLoader` with batch size 32

## CNN Model (Task 4)
A simple but effective CNN built with **PyTorch**:
- 3 convolutional blocks (Conv2d → ReLU → MaxPool2d)
- Flatten → 2 fully connected layers → softmax output

## Training & Evaluation (Task 5)
- Optimizer: Adam (lr=0.001)
- Loss: CrossEntropyLoss
- 10 epochs (early stopping not needed for prototype)
- Metrics: accuracy, confusion matrix, loss/accuracy curves
- Test set performance: displayed in notebook

## CNN Concepts Explained (Task 6)
- **Convolution:** A filter (kernel) slides over the image and computes dot products to detect local patterns (edges, textures, shapes). This creates feature maps that highlight important visual features.
- **Pooling:** Reduces the spatial dimensions of feature maps (e.g., MaxPool2d 2×2). It makes the model more computationally efficient, reduces overfitting, and provides translation invariance.
- **ReLU:** The most common activation function in CNNs. It introduces non-linearity (`f(x) = max(0, x)`) so the network can learn complex patterns. It also helps mitigate the vanishing gradient problem.
- **Why CNNs beat regular feed-forward networks for images?**  
  A plain MLP would require millions of parameters for even small images (each pixel connected to every neuron) and would lose spatial hierarchy. CNNs use **parameter sharing** (same filter across the image) and **local receptive fields**, dramatically reducing parameters while preserving spatial relationships.

## Business Use Case (Task 7) – Manufacturing
In a real-world manufacturing line, this CNN can be deployed on edge devices or cameras above the conveyor belt. It automatically flags defective products (scratch, dent, stain) in real-time, replacing slow and inconsistent manual visual inspection. This reduces waste, improves quality control, lowers labor costs, and prevents defective items from reaching customers – exactly as described in the suggested student tasks.

**Repository also contains:**
- `notebook.ipynb` – complete runnable code
- `requirements.txt`
- Generated plots in `results/` and `sample_predictions/`
