# 🚀 AdInsight AI: Automated Ad Campaign Analysis & Reporting

**Tagline:** A full-stack AI-powered system that ingests raw advertising data, detects anomalies, and generates executive-ready PDF reports with AI-driven insights — all locally without API limits.

---

## 1. Problem (Real World Scenario)

**Context:**  
Digital marketing teams spend hours manually downloading CSVs, calculating KPIs, and creating reports. This process is slow, error-prone, and prevents real-time decision making.

**Pain Point:**  
If an ad campaign underperforms, the client may not know for days. Manual reporting delays actionable insights, leading to wasted budget and lost opportunities.

**Our Solution:**  
AdInsight AI automatically ingests raw advertising datasets, calculates KPIs, detects anomalies using machine learning, and generates AI-powered recommendations in a PDF report. Users simply upload a CSV, and actionable insights are delivered within seconds — **no API limits required**.

---

## 2. Expected End Result

**For the User:**

- **Input:** Drop a raw advertising CSV file into the system.
- **Action:** Wait a few seconds.
- **Output:** Receive a professional PDF containing:
  - Key KPIs: CTR, CPC, ROI, Conversion Rate
  - Week-over-week trend charts
  - Highlighted anomalies
  - AI-generated insights with actionable recommendations

---

## 3. Technical Approach

**System Architecture:**  

1. **Data Ingestion:**  
   - Accepts CSV datasets with columns like `Campaign`, `Impressions`, `Clicks`, `Cost`, `Revenue`, `Conversions`.  
   - Uses Python `pandas`/`polars` for efficient data processing.

2. **Data Cleaning & KPI Calculation:**  
   - Handles missing values and inconsistent formatting.  
   - Calculates KPIs:
     - CTR = Clicks / Impressions  
     - CPC = Cost / Clicks  
     - ROI = Revenue / Cost  
     - Conversion Rate = Conversions / Clicks

3. **Anomaly Detection:**  
   - Uses Isolation Forest to detect unusual campaigns automatically.  

4. **Local AI-Powered Insights:**  
   - Uses **local/open-source LLMs** such as GPT4All, MPT, or LLaMA via Hugging Face transformers.  
   - Generates natural language explanations and recommendations for anomalies **without relying on OpenAI API**.  

5. **Reporting:**  
   - Generates executive-ready PDFs including KPI charts, anomalies, and AI insights.  
   - Uses Plotly for charts and WeasyPrint for PDF rendering.

---

## 4. Tech Stack

- **Language:** Python 3.11  
- **Data Engine:** Pandas / Polars  
- **Machine Learning:** Scikit-Learn (Isolation Forest)  
- **AI Model:** GPT4All / MPT / LLaMA (local Hugging Face models)  
- **Visualization:** Plotly  
- **PDF Rendering:** WeasyPrint  
- **Orchestration:** Google Colab / Docker (optional for production)  

---

## 5. Challenges & Learnings

- **Challenge 1:** Handling AI hallucinations  
  - Solution: Structured prompts and validation to ensure AI only uses provided data.
- **Challenge 2:** Managing large datasets  
  - Solution: Polars DataFrame and event-driven processing for faster performance.
- **Challenge 3:** Avoiding API limits  
  - Solution: Switched to local/open-source LLMs (GPT4All, MPT, LLaMA) to generate insights offline.

---

## 6. How to Run (Google Colab / Local)

1. **Clone Repository**  
```bash
git clone https://github.com/username/adinsight-ai.git
