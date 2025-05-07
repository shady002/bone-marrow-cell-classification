# Fine-Grained Classification of Bone Marrow Blood Cells

This project focuses on the fine-grained classification of 14 bone marrow blood cell types using deep learning techniques. We leverage both a convolutional neural network (ResNet-50) and a transformer-based architecture (Vision Transformer - ViT) for comparative analysis. The dataset is sourced from The Cancer Imaging Archive (TCIA).

## 🔍 Problem Statement

Accurate classification of bone marrow blood cells is essential for diagnosing hematologic diseases such as leukemia and multiple myeloma. Manual microscopy is time-consuming and subject to human error. This project automates cell type classification using deep learning to support more reliable diagnostic decisions.

## 🎯 Objective

To develop a deep learning model that classifies 14 types of bone marrow blood cells with high accuracy, improving the consistency and speed of hematological diagnoses.

## 📁 Dataset

- **Source**: [TCIA Bone Marrow Cytomorphology Dataset](https://www.cancerimagingarchive.net/collection/bone-marrow-cytomorphology_mll_helmholtz_fraunhofer/)
- **Extracted Classes**: 14 distinct cell types (e.g., ART, BLA, EBO, EOS, etc.)
- **Format**: JPEG images categorized in folders by class

## 🧠 Models Used

- **ResNet-50**: Fine-tuned on our dataset for baseline CNN performance
- **ViT (Vision Transformer)**: Pre-trained transformer model applied to medical imaging for improved attention-based feature extraction

## 🛠️ Methodology

1. **Data Preprocessing**:
   - Image normalization
   - Data augmentation (train set)
   - 80/10/10 split for training, validation, testing

2. **Training**:
   - ResNet-50: Trained for 25 epochs with CrossEntropy loss and Adam optimizer
   - ViT: Fine-tuned with transfer learning from pre-trained ImageNet weights

3. **Evaluation**:
   - Accuracy, precision, recall, F1-score
   - Confusion matrix visualization
   - Per-class metrics and error analysis

## 📊 Results

| Model      | Test Accuracy |
|------------|---------------|
| ResNet-50  | 68.36%       |
| ViT        | 80.27%       |

- EOS, PEB, PLM showed higher F1-scores.
- Some classes like MMZ and MON showed class imbalance sensitivity.

## 🖼️ Visualizations

- Confusion matrices
- Per-class predictions with correct/wrong color coding
- GradCAM-style attention maps (optional)

## 🧪 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/bone-marrow-cell-classification.git
   cd bone-marrow-cell-classification
   
2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt

3. **Train or evaluate the models**:

Run resnet50-14c.ipynb for ResNet-50

Run vit-imageclass-14c.ipynb for Vision Transformer (ViT) 

## 📚 References

- **TCIA Dataset Citation**: Lang, U., et al. (2023). *Bone Marrow Cytomorphology (MLL, Helmholtz, Fraunhofer)*. TCIA. https://doi.org/10.7937/TCIA.4V0X-7603
- **ResNet Paper**: He, K., et al. (2016). *Deep Residual Learning for Image Recognition*. CVPR.
- **ViT Paper**: Dosovitskiy, A., et al. (2021). *An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale*. ICLR.

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
