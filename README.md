# Network Traffic Analysis for Intrusion Detection

## 📌 Project Overview
This project focuses on analyzing network traffic data to identify patterns between **Normal Traffic** and **Attack Traffic** using Python-based data analysis techniques. The analysis was performed as part of the **CC5067NI Smart Data Discovery** coursework.

The project uses data preprocessing, statistical analysis, visualization, and hypothesis testing to better understand network behavior and prepare the dataset for future machine learning applications in intrusion detection systems (IDS).

---

# 🎯 Aim
The main aim of this project is to analyze network traffic data using Python libraries and Jupyter Notebook to:

- Understand network flow characteristics
- Compare normal and attack traffic
- Prepare the dataset for future machine learning classification

---

# 📚 Objectives
- Understand the structure of the dataset
- Load and process the dataset using Pandas
- Clean missing and duplicate values
- Perform statistical analysis
- Visualize network traffic behavior
- Compare normal traffic with attack traffic
- Prepare the dataset for machine learning tasks

---

# 🛠️ Tools & Libraries Used

## Programming Language
- Python

## Environment
- Jupyter Notebook

## Python Libraries
- NumPy
- Pandas
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn

---

# 📂 Dataset Information
The dataset contains network traffic flow records with multiple network-related features such as:

- Destination Port
- Flow Duration
- Total Forward Packets
- Total Backward Packets
- Packet Length Features
- Average Packet Size
- Flow Bytes/s
- Traffic Labels

Each record is labeled as:
- **BENIGN** → Normal Traffic
- **Infiltration** → Attack Traffic

## Dataset Size
- **Rows:** 488,115
- **Columns:** 80

After preprocessing:
- **Rows:** 488,079
- **Columns:** 16

---

# ⚙️ Data Preparation Steps

## 1. Load Dataset

```python
import pandas as pd

df = pd.read_csv("network_dataset.csv")
```

## 2. Display Last 50 Records

```python
df.tail(50)
```

## 3. Create New DataFrame

```python
columns = [
    'Destination Port',
    'Flow Duration',
    'Total Fwd Packets',
    'Total Backward Packets',
    'Packet Length Mean',
    'Average Packet Size',
    'Label'
]

new_df = df[columns]
```

## 4. Check Missing Values

```python
new_df.isnull().sum()
```

## 5. Remove Missing Values

```python
new_df = new_df.dropna()
```

## 6. Check Duplicate Records

```python
new_df.duplicated().sum()
```

## 7. Rename Labels

```python
new_df['Label'] = new_df['Label'].replace({
    'BENIGN': 'Normal Traffic',
    'Infiltration': 'Attack Traffic'
})
```

---

# 📊 Statistical Analysis

The following statistical analyses were performed:

## ✔ Sum Analysis
Compared cumulative values of:
- Flow Duration
- Packet Length Mean

## ✔ Mean Analysis
Calculated average values of selected features.

## ✔ Standard Deviation Analysis
Measured variability and spread of data.

## ✔ Skewness Analysis
Observed positive skewness indicating outliers.

## ✔ Kurtosis Analysis
Detected heavy tails and extreme values.

## ✔ Correlation Analysis
Identified highly correlated features such as:
- Packet Length Mean
- Average Packet Size

---

# 📈 Data Visualization

The project includes several visualization techniques:

- Bar Chart
- Pie Chart
- Box Plot
- Histogram
- Line Graph
- Scatter Plot
- Heatmap
- Violin Plot

These visualizations help compare and understand the behavior of normal and attack traffic.

---

# 🧪 Hypothesis Testing

An **Independent T-Test** was performed to compare the mean Flow Duration between Normal Traffic and Attack Traffic.

## Result
- **p-value = 0.474**
- Since `p > 0.05`, the null hypothesis was accepted.

## Conclusion
There is no statistically significant difference in Flow Duration between Normal Traffic and Attack Traffic.

---

#  Key Findings

- The dataset contains slightly more normal traffic than attack traffic.
- Several features contain outliers and positive skewness.
- Some network features are strongly correlated.
- Normal and attack traffic show similar behavior in several statistical analyses.
- The cleaned dataset is suitable for future machine learning applications.

---

# 🚀 Future Improvements

- Apply machine learning classification algorithms
- Build intrusion detection models
- Perform feature engineering
- Handle dataset imbalance
- Use deep learning techniques for attack detection

---

# 📷 Visualizations Included

- Traffic Distribution Bar Chart
- Flow Duration Histogram
- Packet Length Boxplot
- Correlation Heatmap
- Packet Length Scatter Plot
- Violin Plot Analysis

---

# 📖 References

- Python Documentation
- NumPy Documentation
- Pandas Documentation
- Matplotlib Documentation
- Seaborn Documentation
- SciPy Documentation
- Scikit-learn Documentation
- IBM Machine Learning Resources

---

# 👨‍💻 Author

**Eijkeyal Pakhrin**  
