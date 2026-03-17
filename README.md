# Protein Function Prediction using Deep Learning - CAFA 5 🧬

> Research-level deep learning project for predicting protein functions using CNN on CAFA 5 dataset

![Protein Prediction](visuals/14_cnn_training_final.png)

## 🎯 Project Overview

Developed a Convolutional Neural Network (CNN) to predict Gene Ontology (GO) terms for protein sequences, achieving competitive performance on the CAFA 5 (Critical Assessment of Functional Annotation) benchmark dataset.

**Competition:** CAFA 5 - Protein Function Prediction  
**Platform:** Kaggle  
**Task:** Multi-label classification (50 Molecular Function GO terms)

---

## 📊 Key Results

| Metric          | Value   |
|-----------------|---------|
| Hamming Loss    | 0.1448  |
| F1 Score (Micro)| 0.3330  |
| F1 Score (Macro)| 0.0539  |
| Precision       | 0.2259  |
| Recall          | 0.6328  |
| AUPR (Micro)    | 0.3409  |

> ✅ High recall indicates the model predicts many positives; precision is lower due to rare GO term imbalance.

---

## 🧬 What is Protein Function Prediction?

Proteins are essential molecules that perform virtually all functions in living organisms. Each protein has specific functions described by Gene Ontology (GO) terms.

**Challenge:** Millions of proteins are sequenced but their functions are unknown.  
**Solution:** Machine learning can predict functions from amino acid sequences.

---

## 🏗️ Model Architecture

**Optimized CNN (Convolutional Neural Network):**
```
Input (Protein Sequence) 
→ Embedding Layer (32D)
→ Conv1D (64 filters, kernel=3)
→ MaxPooling
→ Conv1D (128 filters, kernel=5)
→ MaxPooling
→ Conv1D (128 filters, kernel=7)
→ GlobalMaxPooling
→ Dense (256)
→ Output (50 GO terms)
```

**Total Parameters:** ~1.5M  
**Training:** Adam optimizer, Binary Cross-Entropy loss

---

## 🚀 Technologies Used

- **Python 3.10**
- **Deep Learning:** TensorFlow/Keras
- **Data Processing:** Pandas, NumPy, BioPython
- **Visualization:** Matplotlib, Seaborn
- **Evaluation:** Scikit-learn

---

## 📂 Project Structure
```
protein-function-prediction-cafa5/
├── data/
│   ├── raw/              # Original CAFA 5 data
│   └── processed/        # Preprocessed sequences
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_extraction.ipynb
│   ├── 03_prepare_training_data.ipynb
│   ├── 04_baseline_models.ipynb
│   └── 05_optimized_cnn_model.ipynb
├── models/
│   └── optimized_cnn_final.h5
├── results/
│   └── cnn_final_results.pkl
├── visuals/             # Plots and figures
├── reports/             # Summaries
└── README.md
```

---

## 🔬 Methodology

### 1. Data Processing
- Loaded CAFA 5 dataset from Kaggle
- Analyzed 500K+ protein-GO annotations
- Selected top 50 Molecular Function GO terms
- Created train/val/test splits (70/15/15)

### 2. Sequence Encoding
- Encoded amino acids as integers
- Vocabulary size: 22 (20 amino acids + padding + unknown)
- Padded sequences to max length 500

### 3. Model Development
- Started with classical ML baselines (RF, XGBoost)
- Developed optimized CNN architecture
- Applied early stopping and learning rate reduction

### 4. Evaluation
- Multi-label classification metrics
- F1-score, Precision, Recall, Hamming Loss
- Per-label performance analysis

---

## 💡 Key Insights

- **CNNs work well** for protein sequences (local patterns matter)
- **Sequence length optimization** crucial for computational efficiency
- **Multi-label classification** is challenging (low subset accuracy)
- **Data imbalance** affects rare GO term predictions

---

## 🎓 Key Learnings

- Deep learning for biological sequences
- Multi-label classification techniques
- Handling imbalanced datasets
- Model optimization for limited resources
- Research project end-to-end workflow

---

## 🔮 Future Work

- [ ] Implement attention mechanisms
- [ ] Use pre-trained embeddings (ProtBERT, ESM)
- [ ] Extend to Biological Process and Cellular Component
- [ ] Incorporate protein structure information
- [ ] Deploy as web API for predictions

---

## 📫 Contact

**Danish Qadeer**
- GitHub: [@Danishqadeer](https://github.com/Danishqadeer)
- Email: danishqadeer75@gmail.com

---

## 📝 Citation

If you use this code, please cite:
```
@misc{qadeer2026protein,
  author = {Danish Qadeer},
  title = {Protein Function Prediction using Deep Learning - CAFA 5},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/Danishqadeer/protein-function-prediction-cafa5}
}
```

---

## 🙏 Acknowledgments

- CAFA 5 organizers for the dataset
- Kaggle for hosting the competition
- TensorFlow/Keras team

---

⭐ If you found this project helpful, please give it a star!

*Last updated: March 2026*
