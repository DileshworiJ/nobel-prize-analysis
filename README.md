# Nobel Prize Winners Analysis (1901–2025)

End-to-end analytics project using the Nobel Prize API: **data ingestion (JSON) → relational tables → EDA → interactive visualizations / dashboard**.

## Project Overview
This project explores long-term trends in Nobel Prize awards from **1901 to 2025**, focusing on category distribution, geographic patterns (birth country), gender representation, and prize-sharing structures.  
The pipeline is designed to be reproducible and easy to extend (e.g., adding new years or extra features).

## Key Features
- Fetches Nobel Prize data from the **official Nobel Prize API (v2.1)** and stores raw JSON snapshots
- Transforms nested JSON into relational tables:
  - `prizes` (one row per prize/year/category)
  - `laureates` (one row per laureate)
  - `prize_laureate` (bridge table for many-to-many relationships)
- Data cleaning & feature engineering (e.g., decade, award year, share fraction)
- Exploratory analysis and interactive visualizations (Plotly)
- Dashboard concept / app (Dash) for filtering by year, category, country, etc.

## Data Source
- Nobel Prize API (v2.1)
- Coverage: 1901–2025
- Notes: country fields are based on available API fields (e.g., birth country / place); some attributes may be missing for older records.

## Data Model (Relational Tables)
- **prizes**
  - `prize_id`, `award_year`, `category`, `date_awarded`, ...
- **laureates**
  - `laureate_id`, `full_name`, `gender`, `birth_date`, `birth_country`, ...
- **prize_laureate**
  - `prize_id`, `laureate_id`, `share`, `motivation`, ...

## Tech Stack
- Python
- Pandas / NumPy
- Plotly
- (Optional) Dash for interactive dashboard
- Jupyter Notebook

## How to Run (Local)
### 1) Clone and create environment
```bash
git clone <YOUR_REPO_URL>
cd <YOUR_REPO_NAME>
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
pip install -r requirements.txt
