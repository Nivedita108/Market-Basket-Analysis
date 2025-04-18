# Market-Basket-Analysis
# 📄 README: Market Basket Analysis using Python & Google Colab

This project demonstrates a simple market basket analysis using a basic grocery aisle dataset and Python's built-in tools. It runs entirely on Google Colab and requires no additional installations.

---

## 📚 Overview
We simulate 1000 random customer transactions from a list of grocery aisle items. Using these transactions, we perform:
- Frequency analysis of items
- Visualization of the most popular aisles
- Pairwise analysis to discover frequently bought together items

---

## 🎓 Key Steps

### 1. 📁 Upload the CSV File
The code allows users to upload a CSV file containing a column named `aisle`. This is done using:
```python
from google.colab import files
uploaded = files.upload()
```

### 2. 🔢 Load and Process Aisle Data
The uploaded file is read into a pandas DataFrame and converted into a list:
```python
aisle_data = pd.read_csv(file_name)
aisle_list = aisle_data['aisle'].tolist()
```

### 3. 🍀 Simulate Random Transactions
We simulate 1000 fake transactions by randomly selecting 1 to 5 items from the aisle list:
```python
for _ in range(1000):
    n_items = random.randint(1, 5)
    basket = random.sample(aisle_list, n_items)
    transactions.append(basket)
```

### 4. 📊 Frequency Analysis
We count how often each aisle appears across all transactions:
```python
item_counts = Counter(all_items)
top_10_items = item_counts.most_common(10)
```

### 5. 📈 Bar Graph Visualization
We plot the top 10 most frequent aisles:
```python
plt.bar(items, counts)
```

### 6. 📊 Pair Co-occurrence Analysis
We find out which item pairs are frequently bought together:
```python
for basket in transactions:
    for pair in combinations(sorted(basket), 2):
        pair_counts[pair] += 1
```

---

## 📆 Output Includes:
- A table showing the top 10 most frequent items
- A bar chart visualizing these top items
- A table of the 10 most frequently bought together item pairs

---

## 🔧 Requirements
Google Colab already includes all the required packages:
- `pandas`
- `matplotlib`
- `random`
- `collections`
- `itertools`

No need to install anything manually!

---

## 📊 Use Cases
This Colab project can be used as a starting point for:
- Retail transaction analysis
- Recommender systems
- Customer behavior simulations

---

## 📅 Author & License
**Created by:** Your Name Here  
**License:** MIT (or your preferred license)

Feel free to fork, improve, and use this as a teaching tool or internal analytics project.

---

Happy Analyzing! 🏦

