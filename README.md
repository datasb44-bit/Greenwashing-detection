# Greenwashing Detection Pipeline 🌿 🔍

An automated pipeline to detect potential "greenwashing" in e-commerce listings by comparing marketing claims (text and images) against consumer sentiment and reviews.

## 🚀 Features

- **Text Analysis:** Lexicon-based detection of environmental claims.
- **Visual Cues:** Uses K-Means clustering to analyze color profiles for "green" imagery.
- **Sentiment Analysis:** Integrates VADER sentiment scores from user reviews.
- **ML Classifier:** A Random Forest model to flag products with high "Claim vs. Review" discrepancy.

## ⚙️ Key Parameters

| Component | Parameter | Value |
|---|---|---|
| K-Means | clusters (k) | 3 |
| K-Means | n_init | 10 |
| Random Forest | n_estimators | 100 |
| Random Forest | max_depth | 10 |
| Random Forest | random_state | 42 |
| Train/test split | test_size | 0.20 |
| Image resizing | IMG_SIZE | 100×100 px |
| Cost function | C_FN / C_FP | 5.0 / 1.0 |

## 🛠️ Installation

1. Clone the repo:
   ```
   git clone https://github.com/datasb44-bit/Greenwashing-detection.git
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Download `amazon.csv` from the Kaggle dataset linked below, place it in the root directory, and update `CSV_PATH` in the script if running locally (default path is `/content/amazon.csv` for Google Colab).

## 📊 Methodology

The model defines **Greenwashing** as:
```
y = 1 if (Text_Claim OR Image_Claim) AND Review_Does_Not_Confirm
```

Dataset: Karkavelraja J. *Amazon Sales Dataset*. Kaggle, 2023. https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

## 📁 Reproducibility

The raw dataset is publicly available on Kaggle (link above). All pipeline parameters and random seeds are logged to `run_config.json` on each run. Train/test split indices are saved as `train_idx.npy` and `test_idx.npy`, enabling exact reproduction of model evaluation. Note that image-derived features (`img_green_flag`, `img_green_ratio`) depend on Amazon URL availability and may vary over time.

## 📄 License

MIT
