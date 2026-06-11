
# 🛒 E-commerce Market Basket Analysis

An unsupervised machine learning pipeline that discovers hidden purchasing patterns in transactional data using the Apriori algorithm.

## 📌 Project Overview
This project acts as the backend logic for an e-commerce "Frequently Bought Together" recommendation engine. Rather than relying on item metadata, it uses pure transactional history to mathematically calculate the probability of items being purchased together based on Support, Confidence, and Lift metrics.

## ⚙️ The Architecture

The pipeline processes raw transactional ledgers through a three-step association rule engine:

1. **Matrix Transformation:**
   - **How it works:** Converts a raw transactional ledger (thousands of individual rows) into a sparse, boolean Market Basket grid (Users x Items).
   
2. **The Apriori Algorithm:**
   - **How it works:** Scans the boolean grid to isolate "Frequent Itemsets," filtering out rare combinations to reduce computational load.

3. **Association Rule Generation:**
   - **How it works:** Calculates the final metrics to define the strength of a rule:
     - **Support:** The baseline frequency of the items being bought together.
     - **Confidence:** The probability of item Y being purchased if item X is in the cart.
     - **Lift:** The ratio of the observed support to that expected if X and Y were independent (Lift > 1 indicates a strong positive association).

## 📊 Dataset
This project utilizes a public Groceries Dataset containing:
- 38,765 individual item purchases.
- 14,963 unique Market Baskets.
- 167 distinct inventory items.

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** MLxtend (Apriori, Association Rules)
* **Environment:** Google Colab / Jupyter Notebook

## 🚀 How to Run

1. Clone this repository:
```bash
git clone [https://github.com/nikamsudarshan/E-commerce-Product-Recommender.git](https://github.com/nikamsudarshan/E-commerce-Product-Recommender.git)
cd E-commerce-Product-Recommender

```

2. Install the required dependencies:
```bash
pip install -r requirements.txt

```


3. Open the Jupyter Notebook:
```bash
jupyter notebook notebooks/market_basket_analysis.ipynb

```


4. Run all cells to process the transactional ledger and output the top hidden purchasing rules.

