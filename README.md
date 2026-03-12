<div align="center">
  <h1>🧠 Predictive AI Inventory Optimization Engine</h1>
  <p><b>Enterprise-grade machine learning pipeline to automate purchasing decisions and optimize inventory levels.</b></p>
  
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn"/>
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
</div>

<br/>

## 🎯 Project Overview
In large-scale retail and healthcare operations, inventory management faces high demand volatility. Traditional historical-data methods often lead to two major bottlenecks: **Stockouts** (missing critical supplies during peak times) and **Overstock** (tied-up capital and high expiration risks).

This project is an **AI-driven inventory platform** that integrates directly with Corporate ERPs via REST APIs. By analyzing multi-variable data using Machine Learning (`scikit-learn`), it predicts future demand with high accuracy and automates the purchasing workflow to maintain optimal stock levels.

### 📈 Business Impact (Projected)
- **Stockout Reduction:** Decreased projected stockouts by **30%** by forecasting demand spikes.
- **Waste Minimization:** Reduced financial losses from expired inventory by an estimated **20%**.
- **Operational Efficiency:** Eliminated manual, spreadsheet dependency by automating the ERP purchasing pipeline.

---

## 🏗️ System Architecture & Data Flow

This system operates as an automated scheduled pipeline (compatible with orchestrators like Kestra or Cron):

1. **Data Ingestion (ETL):** Extracts current inventory levels, historical sales, and external variables from the database (PostgreSQL).
2. **Feature Engineering:** Cleans and structures data using `Pandas` and `NumPy` (handling seasonality, moving averages, and lead times).
3. **Machine Learning Model:** Passes structured data to a Random Forest / Gradient Boosting model (`scikit-learn`) to output a 30-day demand forecast.
4. **Decision Engine:** Compares the forecast against current stock and minimum safety levels to calculate the exact optimal order quantity.
5. **ERP Integration:** Automatically formats the purchasing order and dispatches it to the company's ERP via a `POST` request to the REST API.

---

## 💻 Tech Stack

- **Backend Logic:** Python 3.10+
- **Data Engineering:** Pandas, NumPy, SQLAlchemy
- **Machine Learning:** Scikit-Learn
- **Integration:** Requests (REST APIs), JSON
- **Infrastructure:** Docker, Docker Compose, PostgreSQL

---

## 🚀 Getting Started (Local Development)

### Prerequisites
- Docker and Docker Compose installed.
- Python 3.10+ (if running outside containers).
- A `.env` file with your mock ERP API keys and Database URI.

### Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/lucassantoss4/predictive-inventory-ai.git](https://github.com/lucassantoss4/predictive-inventory-ai.git)
   cd predictive-inventory-ai
