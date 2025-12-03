# groundtruth.mini
 # AdInsight AI: Automated Ad Campaign Analysis & Reporting H-001
 

**Tagline:** A full-stack AI-powered system that ingests raw advertising data, detects anomalies, and generates executive-ready PDF reports with AI-driven insights.

---

## 1. Problem (Real World Scenario)

**Context:**  
Digital marketing teams spend hours manually downloading CSVs, calculating KPIs, and creating reports. This process is slow, error-prone, and prevents real-time decision making.

**Pain Point:**  
If an ad campaign underperforms, the client may not know for days. Manual reporting delays actionable insights, leading to wasted budget and lost opportunities.

**Our Solution:**  
AdInsight AI automatically ingests raw advertising datasets, calculates KPIs, detects anomalies using machine learning, and generates AI-powered recommendations in a PDF report. Users simply upload a CSV, and actionable insights are delivered within seconds.

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
   - Accepts CSV datasets with columns like `campaign_number`, `displays`, `clicks`, `cost`, `revenue`, `post_click_conversions`.  
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
   - Optionally uses Z-score to detect numeric outliers.

4. **AI-Powered Insights:**  
   - Generates natural language explanations and recommendations for anomalies.  
   - Uses OpenAI GPT-4o / Google Gemini with structured prompts.  

5. **Reporting:**  
   - Generates executive-ready PDFs including KPI charts, anomalies, and AI insights.  
   - Uses Plotly for charts and WeasyPrint for PDF rendering.

---

## 4. Tech Stack

- **Language:** Python 3.11  
- **Data Engine:** Pandas / Polars  
- **Machine Learning:** Scikit-Learn (Isolation Forest)  
- **AI Model:** OpenAI GPT-4o / Google Gemini  
- **Visualization:** Plotly  
- **PDF Rendering:** WeasyPrint  
- **Orchestration:** Google Colab / Docker (optional for production)  

---

## 5. Challenges & Learnings

- **Challenge 1:** Handling AI hallucinations  
  - Solution: Structured prompts and validation to ensure AI only uses provided data.
- **Challenge 2:** Managing large datasets  
  - Solution: Polars DataFrame and event-driven processing for faster performance.
- **Challenge 3:** OpenAI API changes  
  - Solution: Updated to Chat API (`openai.chat.completions.create`) with latest library version.

---

## 6. How to Run (Google Colab / Local)

1. **Clone Repository**  
```bash
git clone https://github.com/username/adinsight-ai.git
