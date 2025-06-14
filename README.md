# Data-Analyst-Agent-using-LLaMA-4-Maverick

# # 🧠 Data Analyst Agent

This notebook enables a user to upload a dataset (Excel, CSV, PDF, image, etc.), analyze the data, ask follow-up questions, and generate visualizations.

---

## 🗂️ 1. Setup

```python
!pip install pandas matplotlib seaborn openpyxl pymupdf
```

---

## 📤 2. Upload File

```python
from google.colab import files
uploaded_file = files.upload()
```

---

## 📄 3. File Reading Utility

```python
import pandas as pd
import io

file_content = io.BytesIO(uploaded_file['your_filename.xlsx'])  # Replace with your uploaded file
df = pd.read_excel(file_content)
df.head()
```

---

## 📊 4. Data Analysis Example

```python
df.describe()
df.info()
```

---

## 🧮 5. Ask Questions About Data

```python
# Example: What are the most frequent values?
df['ColumnName'].value_counts().head(10)
```

---

## 📈 6. Data Visualizations

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 5))
sns.histplot(df['ColumnName'], kde=True)
plt.title('Distribution of ColumnName')
plt.show()
```

---

## 🧼 7. Data Cleaning (Optional)

```python
df.isnull().sum()
df = df.dropna()
```

---

## 💾 8. Export Processed File

```python
df.to_csv('processed_data.csv', index=False)
files.download('processed_data.csv')
```

---

## ✅ Summary

This notebook allows:
- Uploading files (Excel, CSV, PDF, Image)
- Analyzing the data (describe, info)
- Asking questions about the data
- Visualizing the data
- Exporting cleaned/processed data

Feel free to customize the logic as per your data and needs!
