# BUA451-FinalProject-Dapeng-Shen

# Google Trends Analysis and Trend Prediction

## Project Description
This project analyzes U.S. Google Trends data to identify patterns in rising search terms and predict high-impact trends. It includes exploratory data analysis (EDA) to uncover seasonal trends and a Decision Tree classification model to predict whether a term's popularity score exceeds a threshold (score > 60). The model achieved 88.8% accuracy, providing actionable insights for strategic marketing and trend forecasting.

## Dataset
- **Source**: `bigquery-public-data.google_trends.top_rising_terms` (Google Trends public dataset on BigQuery).
- **Time Range**: 2020–2025.
- **Key Fields**:
  - `term`: Search keyword/phrase.
  - `rank`: Term's position among top risers.
  - `percent_gain`: Percentage increase in search interest.
  - `score`: Numeric value indicating trend strength (target variable).
  - `refresh_date`, `week`, `dma_name`, `dma_id`: Temporal and regional metadata.

## Key Findings
### EDA Results
1. **Top Rising Terms**:  
   - Educational platforms ("kahoot," "blooket") and sports terms ("barcelona," "uefa champions league") dominate.
   - *Implication*: Highlights opportunities for EdTech and sports-related marketing.
   
2. **Monthly Trends**:  
   - Peaks in January and May, troughs in February and April.
   - *Implication*: Align campaigns with cyclical interest spikes.

### Predictive Modeling
- **Model**: Decision Tree classifier (max depth=5).
- **Features**: Rank, day of week, DMA region, and historical trend presence.
- **Performance**:
  - Accuracy: **88.8%**.
  - High precision for low-score terms (score ≤ 60) but low recall for high-score terms (score > 60).
  - *Implication*: Effective for filtering noise but limited in detecting emerging trends.

## Installation
1. **Libraries**:
   ```bash
   pip install pandas google-cloud-bigquery plotly
