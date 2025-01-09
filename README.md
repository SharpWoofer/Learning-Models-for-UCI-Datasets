# D7041E Mini Project Report

## Group Members
- **Cai Hongqi** ([honcai-4@student.ltu.se](mailto:honcai-4@student.ltu.se))  ID: 010924-T398
- **Nityasundar Rajakumar** ([nitraj-4@student.ltu.se](mailto:nitraj-4@student.ltu.se))  ID: 010314-T453
- **Poh Qi Bin** ([qibpoh-4@student.ltu.se](mailto:qibpoh-4@student.ltu.se))  ID: 011013-T455

GitHub Repository: [Learning Models for UCI Datasets](https://github.com/SharpWoofer/Learning-Models-for-UCI-Datasets)

---

## Addressed Grading Criteria
- Developed **1 unsupervised** (KMeans) and **1 supervised** (Random Forest) classification model.
- Evaluated models on 5 datasets from the **UCI repository**.
- Reported classification accuracy and clustering metrics.

---

## Datasets
### 1. Dermatology  
- **Description:** Clinical and histopathological features for diagnosing skin diseases, including family history and age. Features are measured on a scale of 0-3.

### 2. Flags   
- **Description:** Features of national flags, including numeric, Boolean, and nominal values. Target variable represents the flag's class.

### 3. Steel Plates Faults   
- **Description:** Steel plate fault classification into 7 types (e.g., Pastry, Z_Scratch, Dirtiness). Used for automatic pattern recognition.

### 4. Wine   
- **Description:** Chemical analysis of wines from 3 cultivars. Features include alcohol content, acidity, and other chemical properties.

### 5. Zoo   
- **Description:** Simple dataset with Boolean-valued attributes. Classes represent different types of animals.

---

## Models
### 1. Unsupervised: **KMeans**
- **Key Hyperparameters:**
  - `n_clusters`: Number of unique labels in dataset.
  - `random_state`: Fixed to 42 for reproducibility.
  - Default parameters used for other hyperparameters.

### 2. Supervised: **Random Forest**
- **Key Hyperparameters:**
  - `n_estimators`: 100 (default)
  - `criterion`: 'gini' (default)
  - `random_state`: Fixed to 42 for reproducibility.
  - Default parameters used for other hyperparameters.

---

## Experimental Methodology
- **Dataset Splits:** 80% training, 20% testing (random seed 42).
- **Cross-Validation:** Grid Search with 3-fold cross-validation for Random Forest.
- **Performance Metrics:**
  - **Random Forest:** Accuracy, precision, recall, F1-score.
  - **KMeans:** Adjusted Rand Index (ARI), Silhouette Score (suggested).

---

## Results Summary
| Dataset         | ARI (KMeans) | Accuracy (Random Forest) |
|-----------------|--------------|--------------------------|
| Dermatology     | 0.68         | 0.99                     |
| Flags           | 0.12         | 0.59                     |
| Steel Faults    | 0.23         | 0.78                     |
| Wine            | 0.92         | 1.00                     |
| Zoo             | 0.47         | 0.95                     |

---

## Key Insights
- **Best Performance:**  
  - **Wine dataset:** ARI = 0.92 (KMeans), Accuracy = 1.00 (Random Forest).  
  - **Dermatology dataset:** High performance for both models.
- **Challenges:**  
  - **Flags dataset:** Poor clustering (ARI = 0.12) and moderate classification accuracy (0.59).  
  - **Steel Faults dataset:** Random Forest outperforms KMeans significantly.

---

## Conclusion
- **Random Forest** generally achieves higher accuracy across datasets, showcasing its effectiveness for supervised classification.  
- **KMeans** performs well on structured datasets (e.g., Wine) but struggles with complex or imbalanced datasets (e.g., Flags).  
- Dataset diversity highlights model strengths and limitations, emphasizing the importance of dataset characteristics in machine learning.
