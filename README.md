# Greenwashing Detection Pipeline 🌿🔍

An automated pipeline to detect potential "greenwashing" in e-commerce listings by comparing marketing claims (text and images) against consumer sentiment and reviews.

## 🚀 Features
- **Text Analysis:** Lexicon-based detection of environmental claims.
- **Visual Cues:** Uses K-Means clustering to analyze color profiles for "green" imagery.
- **Sentiment Analysis:** Integrates VADER sentiment scores from user reviews.
- **ML Classifier:** A Random Forest model to flag products with high "Claim vs. Review" discrepancy.

## 🛠️ Installation
1. Clone the repo: `git clone https://github.com/datasb44-bit/greenwashing-detector.git`
2. Place your `amazon.csv` in the root directory.

## 📊 Methodology
The model defines **Greenwashing** as:
`y = 1 if (Text_Claim OR Image_Claim) AND Review_Does_Not_Confirm`

Dataset Configuration
Place your amazon.csv file in the root directory.
Note: Dataset used:https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset
