# Comparative Analysis of Feature Extraction Techniques on MNIST

This project explores a variety of feature extraction methods for the MNIST handwritten digit dataset. We evaluate how different representations affect classification accuracy, dimensionality, and computational efficiency using a consistent classifier setup.

## Objective

To compare the feature extraction methods:
- Raw pixel intensities
- PCA (Principal Component Analysis)
- Fixed convolutional filters (e.g., Sobel, Prewitt, Laplacian, Gaussian)
- Learned CNN-based encodings
- Autoencoder-based encodings

using a Random Forest classifier trained on each representation.

## Dataset

**MNIST handwritten digits**  
- Source: [Kaggle MNIST Original](https://www.kaggle.com/datasets/avnishnish/mnist-original)
- 70,000 images of size 28x28
- 80/20 train-test split, stratified by digit label

## Setup

1. **Clone this repo** and navigate into it:

   ```
   git clone https://github.com/theosiemensrhodes/mnist-feature-extraction
   cd mnist-feature-extraction
   ```

2. **Create a virtual environment and activate it**:

   ```
   python3 -m venv .venv
   source .venv/bin/activate  # macOS/Linux
   .venv\Scripts\activate     # Windows
   ```

3. **Install required packages**:

   ```
   pip install -r requirements.txt
   ```

4. **Launch the notebook**:

   ```
   jupyter notebook src/project.ipynb
   ```

## Results Summary

| Method                          | Dimensionality | Test Accuracy |
|---------------------------------|----------------|---------------|
| CNN Encoded                     | 128            | 98.5%         |
| Autoencoded + PCA               | 32             | 95.3%         |
| Fixed Convolution Encoded       | 150            | 96.1%         |
| Raw Pixels                      | 784            | 96.6%         |
| Raw Pixels + PCA                | 128            | 94.4%         |

CNN-derived features consistently outperform other methods, even at low embedding dimensions.

## Report

See `CPEN_355_Final_Project.pdf` for:
- Full methodology
- Diagrams of network architectures
- Accuracy breakdown by method
- Discussion on dimensionality and model efficiency

## References

- [Kaggle MNIST Dataset](https://www.kaggle.com/datasets/avnishnish/mnist-original)
- [Feature Extraction with Classical Filters](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7829626&tag=1)
- [Noise Filtering Techniques in Image Processing](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10817575/#:~:text=originate%20from%20the%20image%20sensor,Gaussian%2C%20Mean%2C%20and%20Median%20filters)

---

**Author:** Theo Siemens-Rhodes  
**Affiliation:** University of British Columbia, Electrical and Computer Engineering  
