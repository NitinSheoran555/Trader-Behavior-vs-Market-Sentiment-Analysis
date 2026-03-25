# Crypto Fear & Greed Index — Analysis

# Intern Project** | Period covered: Feb 2018 – Sep 2024 | 2,644 daily observations


## Project Structure


 fear_greed_analysis.ipynb   # Main analysis notebook 
 fear_greed_index.csv        # Source dataset
 README.md                   # This file
 charts/
 chart1_timeline.png     # Daily scatter  - full timeline
 chart2_distribution.png # Sentiment class distribution 
 chart3_monthly_avg.png  # Monthly rolling average (fear/greed shading)
 chart4_yearly.png       # Yearly sentiment breakdown (stacked bar) 
 chart5_transitions.png  # Sentiment transition probability heatmap
 chart6_histogram.png    # Value distribution per sentiment class

---

## Requirements 

| Package     | Version  |

| Python      |  3.9    |
| pandas      | any recent |
| matplotlib  | any recent |
| seaborn     | any recent |

Install dependencies:

bash
pip install pandas matplotlib seaborn




## How to Run

### Option A — Jupyter Notebook (recommended)

```bash
# Clone / download project files, then:
jupyter notebook fear_greed_analysis.ipynb
```

Run all cells top-to-bottom (`Kernel → Restart & Run All`).  
Make sure `fear_greed_index.csv` is in the **same directory** as the notebook.

### Option B — JupyterLab

```bash
jupyter lab fear_greed_analysis.ipynb
```

### Option C — Convert to script and run headlessly

```bash
jupyter nbconvert --to script fear_greed_analysis.ipynb
python fear_greed_analysis.py
```

> **Note:** When running as a script, `plt.show()` calls will produce no window. Add `plt.savefig(...)` before each `plt.show()` call to save charts to disk instead.

---

## Dataset Description

| Column         | Type   | Description                                      |
|----------------|--------|--------------------------------------------------|
| `timestamp`    | int64  | Unix timestamp (seconds)                         |
| `value`        | int64  | Fear & Greed index value (0 = max fear, 100 = max greed) |
| `classification` | str  | Categorical label (Extreme Fear / Fear / Neutral / Greed / Extreme Greed) |
| `date`         | str    | Human-readable date (M/D/YY format)              |

---

## Analysis Summary

See **Section 5** of the notebook for full insights and strategy recommendations.  
High-level findings:

- The market spent ~49% of days in Fear/Extreme Fear vs ~36% in Greed/Extreme Greed.
- Extreme sentiment regimes are persistent: average streak of ~5–6 days, max 74–77 days.
- Median recovery time from Fear to Greed: **15 days** (mean: 38.6 days, highly right-skewed).
- Sentiment autocorrelation is strong: today's sentiment predicts tomorrow's with 60–75% accuracy.
