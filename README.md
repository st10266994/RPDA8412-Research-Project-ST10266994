# 🧠 Predicting Belief in AI-Generated Political Misinformation

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-models-F7931E?logo=scikitlearn&logoColor=white)
![Status](https://img.shields.io/badge/status-final%20submission-brightgreen)

Research project for **RPDA8412**. The study tests whether the metaphors, emotions and engagement attached to political misinformation relate to how strongly people believe it, and whether belief can be predicted from this information.

**Author:** Alyssia Sookdeo (ST10266994)

---

## 🎯 What the study does

**Phase 1: relationships between variables**
- 🔗 Pearson correlations between emotion intensity, engagement and belief score
- 📊 Kruskal-Wallis test of belief score across metaphor types

**Phase 2: classification**
- 🏷️ Predicts `Belief_Label` (the target) using three models:
  - Naive Bayes
  - Random Forest
  - BERT, fine-tuned on the cleaned text

---

## 📂 Repository contents

| File | Description |
|---|---|
| 📓 `research.ipynb` | Full analysis notebook |
| 🗃️ `misinformation_metaphors_dataset.csv` | Dataset, 1,500 records and 14 columns |
| 🧾 `class_balance_summary.csv` | Counts and percentages of each belief class |
| 🧹 `data_cleaning_log.csv` | Record of each cleaning step |
| 📈 `descriptive_statistics.csv` | Mean, median, spread and skewness of the numeric variables |
| ❓ `missing_value_summary.csv` | Missing values per column |
| 🖼️ `*.png` | Figures produced by the notebook |

### Figures

| Figure | File |
|---|---|
| Class balance | `class_balance.png` |
| Categorical frequencies | `categorical_frequencies.png` |
| Numeric distributions | `numeric_distributions.png` |
| Outlier boxplots | `outlier_boxplots.png` |
| Correlation matrix | `correlation_matrix.png` |
| Emotion intensity by belief label | `emotion_intensity_by_belief_label.png` |
| Engagement by belief label | `engagement_by_belief_label.png` |
| Confusion matrices | `confusion_matrices.png` |
| ROC curves | `roc_curves.png` |
| Random Forest feature importance | `random_forest_feature_importance.png` |

---

## 🗄️ Dataset

Each record is one piece of political misinformation text with its metaphor type, evoked emotion, topic, a participant's belief rating and its engagement counts.

| Column | Type | Meaning |
|---|---|---|
| `Sample_ID` | String | Record identifier |
| `Source_Type` | String | Origin of the content |
| `Platform` | String | Platform the content appeared on |
| `Content_Text` | String | Text of the content |
| `Metaphor_Type` | String | Metaphor category |
| `Emotion_Evoked` | String | Emotion the content evokes |
| `Political_Topic` | String | Topic of the content |
| `Participant_ID` | String | Anonymised participant identifier |
| `Belief_Score` | Float | Belief rating |
| `Emotion_Intensity_Score` | Float | Strength of the emotion |
| `Belief_Label` | Integer | Binary belief class (target) |
| `Engagement_Likes` | Integer | Number of likes |
| `Engagement_Shares` | Integer | Number of shares |
| `Date_Posted` | Date | Date of posting |

---

## ▶️ Running the notebook

1. Clone the repository:
   ```bash
   git clone https://github.com/st10266994/RPDA8412-Research-Project-ST10266994.git
   cd RPDA8412-Research-Project-ST10266994
   ```
2. Install the libraries the notebook imports:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy scikit-learn nltk transformers torch accelerate jupyter
   ```
3. Open `research.ipynb` in Jupyter or VS Code and choose **Run All**. Keep the CSV files in the same folder as the notebook.

> ⚠️ The BERT fine-tuning step is slow without a GPU, and its output folder (`bert_output/`) is not included in this repository.
