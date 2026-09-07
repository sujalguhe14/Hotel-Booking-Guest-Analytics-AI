🏨 Executive Hotel Booking & Guest Analytics Suite (with Python AI Predictor)
PythonScikit-LearnPandasMySQLPower BIWeb BI

An executive-style Hotel Booking Analytics & AI Machine Learning Suite designed for hotel general managers, revenue directors, and operations leads. This end-to-end intelligence platform combines traditional BI dashboards with an easy-to-use Python AI Cancellation Risk Predictor engine.

🤖 New Feature: Easy Python AI Machine Learning Engine
The project now includes an easy-to-understand Random Forest AI Classifier (scripts/ai_cancellation_predictor.py) built with scikit-learn that predicts booking cancellations and quantifies financial risk factors:

AI Model: Random Forest Classifier trained on 15,000 reservation records.
Risk Scoring: Scores every reservation with an AI Cancellation Probability (0%–100%) and assigns a risk tier (Low Risk, Medium Risk, High Risk).
Feature Importance Ranking:
Average Daily Rate (ADR) (26.8% influence): Higher room rates increase cancellation sensitivity.
Lead Time (24.8% influence): Bookings created far in advance have the highest cancellation rates.
Hotel Type (12.4% influence): City Hotels experience higher drop-off rates than Resort Hotels.
Total Stay Nights (11.6% influence): Longer stay durations increase booking volatility.
Booking Changes (4.2% influence): Frequent modifications signal potential cancellation.
🎯 Business Goal & Primary Questions
The primary objective of this dashboard is to answer core commercial and operational questions:

Revenue Drivers: Which hotel types (City Hotel vs Resort Hotel), room tiers, customer groups, and booking periods generate the most realized revenue?
Cancellation Hotspots: Where, when, and among which customer segments are cancellations occurring, and what is the estimated monetary revenue loss?
AI Risk Forecasting: Which individual reservations are at highest risk of cancelling, and what proactive actions should hotel management take?
Relationship Dynamics: How do booking channels and customer segments connect to cancellation outcomes?
📊 Executive Core KPIs & Formulas
Core Metric	Calculation / Logic	Accent Color	Description
Total Revenue	SUM(ADR * (stays_in_week_nights + stays_in_weekend_nights))	Cyan #06B6D4	Gross potential value of all reservations
Realized Revenue	SUM(Revenue) WHERE is_canceled = 0	Emerald #10B981	Revenue collected from completed check-outs
Revenue Lost	SUM(Revenue) WHERE is_canceled = 1	Rose #EF4444	Financial leakage from cancelled bookings
Total Bookings	COUNT(booking_id)	Blue #3B82F6	Total volume of reservations generated
Cancelled Bookings	COUNT(booking_id) WHERE is_canceled = 1	Coral #F43F5E	Count of cancellations and no-shows
Cancellation Rate	Cancelled Bookings / Total Bookings	Crimson #DC2626	Percentage of total reservations cancelled
Average Daily Rate (ADR)	AVERAGE(adr)	Amber #F59E0B	Average price paid per room night
Avg Length of Stay	AVERAGE(stays_in_week_nights + stays_in_weekend_nights)	Purple #8B5CF6	Average stay duration in nights
Repeat Guest Rate	COUNT(is_repeated_guest = 1) / Total Bookings	Indigo #6366F1	Percentage of returning loyal guests
🛠️ Toolstack & Project Workflow
The project follows a multi-tier analytics and machine learning pipeline:


[ Data Collection & Excel ] ──> [ Python Pandas Data Pipeline ] ──> [ Scikit-Learn AI ML Model ]
                                                │                                   │
                                                ├──> [ Matplotlib & NetworkX ]      ├──> [ AI Predictions CSV ]
                                                ├──> [ MySQL DB Schema & Views ]    └──> [ AI Feature Importance Plot ]
                                                ├──> [ Power BI DAX & Theme ]
                                                └──> [ Executive Web BI App + Live AI Simulator ]
Excel: Conceptual data structure, collection, and initial data verification.
Pandas & NumPy: Data transformations, feature engineering (revenue, realized_revenue, revenue_lost, lead_time_bucket, guest_count), null handling, and aggregation.
Scikit-Learn (AI / ML): Easy-to-use Random Forest model for cancellation probability prediction and feature importance extraction.
Matplotlib & Seaborn: Static high-resolution executive charts for presentations and executive decks.
NetworkX: Directed graph analysis mapping connections between Customer Type → Distribution Channel → Hotel Type → Cancellation Outcome.
MySQL: Production DDL, performance indexes, executive analytical views (view_hotel_kpis), and queries answering core business questions.
Power BI: Full DAX measure library, custom Dark Executive Theme (executive_theme.json), and 3-page layout guide.
Executive Web BI Application: Modern single-page interactive dashboard (HTML5, CSS3, JavaScript, Chart.js, HTML5 Canvas) featuring real-time slicers, dynamic Smart Narratives, and an Interactive AI Booking Risk Simulator.
📁 Repository Structure

.
├── index.html                          # Executive Web BI Dashboard Application UI (with AI Simulator)
├── css/
│   └── dashboard.css                   # Executive dark slate styling (Glassmorphism, responsive grid)
├── js/
│   ├── data.js                         # JavaScript dataset & dynamic filtering calculation engine
│   ├── app.js                          # Dashboard controller, slicers, Chart.js & AI Simulator engine
│   └── network_graph.js                # Interactive HTML5 Canvas NetworkX visualizer
├── data/
│   ├── hotel_bookings_processed.csv    # Cleaned & feature-engineered dataset (15,000 records)
│   ├── hotel_ai_predictions.csv        # Enriched dataset with AI cancellation probabilities & risk tiers
│   ├── ai_model_summary.json           # Exported AI evaluation metrics & feature importances
│   └── network_graph_data.json         # NetworkX exported graph nodes and edges
├── scripts/
│   ├── data_pipeline.py                 # Python data cleaning & feature engineering script
│   ├── ai_cancellation_predictor.py    # Easy Python AI Scikit-Learn Random Forest model script
│   └── network_graph_analysis.py       # Standalone NetworkX relationship graph generator
├── database/
│   └── schema_and_queries.sql          # MySQL DDL, indexes, analytical views & queries
├── powerbi/
│   ├── executive_theme.json            # Power BI dark executive theme config JSON
│   ├── dax_measures.dax               # Complete library of DAX formulas
│   └── power_bi_layout_guide.md        # Detailed 3-page layout guide for Power BI
├── images/                             # Generated high-resolution visual charts
│   ├── revenue_by_hotel_type.png
│   ├── revenue_by_room_type.png
│   ├── adr_vs_cancellation_combo.png
│   ├── lead_time_cancellation.png
│   ├── ai_feature_importance.png       # Generated AI ML feature importance chart
│   └── network_relationship_graph.png
└── README.md                           # Master GitHub documentation
🖥️ Executive Web BI Dashboard Views
Multi-Filter Slicers Bar: Filter simultaneously across 8 dimensions (Hotel Type, Arrival Year, Arrival Month, Room Type, Customer Type, Market Segment, Distribution Channel, Cancellation Status).
4 Structured Navigation Views:
📊 Overview: 9 KPI cards, Monthly Revenue Trend line chart, and ADR vs. Cancellation Rate dual-axis combo chart.
💰 Revenue Drivers: Ranked Bar Chart (City vs Resort), Horizontal Bar Chart by Room Tier, and Customer Segment breakdown.
⚠️ Cancellation Analysis: Cancellation Rate by Lead Time Windows (0–30, 31–90, 91–180, 180+ days), Revenue Loss by Channel, and Interactive NetworkX Canvas Graph.
🤖 AI Risk Predictor: Live interactive reservation risk calculator where users tweak Lead Time, ADR, Deposit Type, Market Segment, Nights, and Previous Cancellations to compute real-time AI Risk Scores (%) and revenue guidance.
Dynamic Smart Narrative Engine: Recalibrates text insights automatically whenever any filter is adjusted.
🚀 Quick Start Guide
1. Web Dashboard & AI Simulator (Local Host)
Launch the web application locally using Python's built-in HTTP server:

bash

# Navigate to project directory
cd "Hotel mini project ai"
# Start local web server on port 8080
python -m http.server 8080
Open your browser and navigate to: http://localhost:8080

2. Python Data Pipeline & AI Model Execution
To re-run data cleaning, train the Python AI classifier, and regenerate charts:

bash

# Install dependencies
pip install pandas numpy matplotlib seaborn networkx scikit-learn
# Run data pipeline
python scripts/data_pipeline.py
# Run Easy Python AI Cancellation Predictor Model
python scripts/ai_cancellation_predictor.py
# Run NetworkX graph analysis
python scripts/network_graph_analysis.py
3. MySQL Database Setup
Import the database schema and analytical queries:

sql

-- In MySQL Workbench or CLI
SOURCE database/schema_and_queries.sql;
4. Power BI Desktop Setup
Open Power BI Desktop.
Load data/hotel_bookings_processed.csv or data/hotel_ai_predictions.csv.
Import powerbi/executive_theme.json via View > Themes > Browse for themes.
Copy-paste DAX formulas from powerbi/dax_measures.dax.
Arrange visuals following powerbi/power_bi_layout_guide.md.
💡 Key Findings & Business Insights
🏆 Leading Revenue Hotel: City Hotel accounts for 66.4% of realized revenue ($2.64M), outperforming Resort Hotel ($1.34M).
🤖 Top AI Risk Factor: Average Daily Rate (ADR) and Lead Time account for over 51% of total cancellation risk prediction.
🛏️ Strongest Room Tier: Room Type A generates over 60% of total realized revenue due to high booking volume.
📅 Seasonality Peak: August is the top revenue-generating month, coinciding with peak European vacation periods.
⚠️ Cancellation Risk Window: Bookings created 180+ days in advance exhibit a cancellation rate exceeding 50%, compared to under 20% for bookings made within 0–30 days.
💸 Financial Impact: Cancellations resulted in an estimated revenue leakage of $2.31M (36.8% of potential total revenue).

📜 License
Distributed under the MIT License. See LICENSE for details.
