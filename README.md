# 💹 Cryptocurrency Data Fetching and Analysis using Python API

## 📘 Project Overview
This project focuses on **retrieving and analyzing real-time cryptocurrency data** using public **APIs** with **Python**.  
The goal was to collect live data such as coin prices, market capitalization, and trading volumes — process it using **Pandas**, and make it ready for further analytics or visualization.

---

## 🧩 Tools and Technologies
- **Python 3** — core programming language  
- **Jupyter Notebook** — for development and testing  
- **Requests Library** — for API communication  
- **Pandas** — for data cleaning and analysis  
- **JSON** — for handling API responses  

---

## ⚙️ Project Workflow

### 1. API Integration
- Connected to a public crypto API (e.g., CoinGecko or CoinMarketCap).  
- Retrieved live cryptocurrency data in **JSON** format.  
- Extracted key fields like coin name, symbol, price, and market cap.

### 2. Data Extraction
- Parsed API responses using Python’s `requests` and `json` modules.  
- Stored structured results into a **DataFrame** using **pandas**.  
- Displayed clean tabular outputs directly in the notebook.

### 3. Data Cleaning & Processing
- Removed missing or null values.  
- Converted prices and volumes into numeric data types.  
- Renamed columns for better readability and analysis.

### 4. Data Export
- Saved final processed data into a **CSV file** (`crypto_data.csv`) for reporting or visualization.  
- Ensured file is updated automatically when API data changes.

---

## 🧮 Example Code Snippet
```python
import requests
import pandas as pd

url = "https://api.coingecko.com/api/v3/coins/markets"
params = {'vs_currency': 'usd'}
response = requests.get(url, params=params)
data = response.json()

df = pd.DataFrame(data, columns=['id', 'symbol', 'current_price', 'market_cap', 'total_volume'])
df.head()
