# SpendDNA — Rahul's Wallet, Decoded 💸

Turns 6 months of messy UPI/bank transaction data into a Spotify-Wrapped-style financial personality report, using nothing but Python, Pandas, and NumPy.

## 📸 Output

<img width="586" height="925" alt="Screenshot 2026-07-04 165856" src="https://github.com/user-attachments/assets/62ccc689-a7fa-49ec-afe8-fac692b6f4e4" />

## 🚫 Constraints

What this project deliberately **does** and **does not** use:

| Allowed | Forbidden |
|---|---|
| Python fundamentals (loops, dicts, functions) | `matplotlib` / `seaborn` — every visual is plain-text ASCII |
| `pandas` (groupby, pivot_table, `.str` methods, `.dt` accessor) | `scikit-learn` / `scipy` — z-scores computed manually |
| `numpy` (arrays, `.mean(axis=...)`, vectorised ops) | `re` / regex — vendor matching uses plain `in` string checks |
| Keyword-dictionary string matching for vendor extraction | `collections.Counter` — counts done via `pandas.value_counts()` |
| Manual z-score formula for anomaly detection | Any pre-built NLP/fuzzy-matching library |

The constraint is the point: cleaning ~280 raw vendor description variants down to 41 canonical vendors using only `if kw in string.upper()` checks (no regex) is what the exercise is actually testing.

## ▶️ How to run

1. Clone or download this repo.
2. Open `SpendDNA_Parvathy_M.ipynb` in [Google Colab](https://colab.research.google.com/).
3. Upload `rahul_transactions.csv` to the Colab session (folder icon on the left → upload).
4. Runtime → Run all.

No installation needed — `pandas` and `numpy` are pre-installed in Colab. Runs end-to-end with no errors.

## 🗂️ Repo contents

- `SpendDNA_Parvathy_M.ipynb` — the full analysis notebook (8 core features + 3 bonus features)
- `rahul_transactions.csv` — the source dataset (1,328 rows, Jan–Jun 2024)
- `README.md` — this file

## 📊 What it found

- **41 canonical vendors** extracted from **283 raw description variants**, 0 left uncategorised
- **E-commerce is the #1 spending category** (~37% of spend), driven by a handful of large Amazon/Flipkart orders
- **Savings rate is deeply negative** — spend consistently outpaces income across all 6 months
- Archetypes triggered: **The Shopaholic**, **The Investor**, **The YOLO Spender**, and the invented **Solo Shopaholic** (any single vendor > 15% of total spend — Amazon alone is ~20%)

## ✍️ Author

**Parvathy M**
