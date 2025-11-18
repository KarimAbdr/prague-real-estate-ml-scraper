Prague Real Estate Investment Analysis
Bachelor thesis project analyzing Prague rental and sales markets using machine learning to predict rental income and calculate investment payback periods.
🎯 Project Overview
This project collects data from Czech real estate portals (Bezrealitky & Sreality), trains ML models to predict rental prices, and estimates investment returns for apartments listed for sale.
Key Question: How long would it take for a Prague apartment to pay for itself through rental income?
📊 Data Collection

Sources: Bezrealitky and Sreality APIs
Data Types: Apartments for rent & sale in Prague
Features: Price, location (district), size, disposition, furnishing, coordinates
Note: Rental prices exclude utilities (paid separately by tenants)

🤖 Machine Learning Pipeline
Models Compared

Random Forest Regressor
Ridge Regression
Lasso Regression
ElasticNet

Custom Pipeline Components
1. Data_splitter

Splits data into: train, test, and unknown (missing furnishing data)

2. Encoder

Disposition: Ordinal encoding (room count)
District: Target encoding (average price by district)
Furnishing: One-hot encoding

3. FurnishingImputer

Uses RandomForestClassifier to predict missing furnishing values (~25% of data)
Treats imputation as a supervised learning problem

Encoding Strategy

Imputation stage: Count encoding for districts (prevents target leakage)
Final model: Target encoding for districts (captures price patterns)

📈 Analysis & Results
Investment Metrics

Predicted annual rental income for each property
Payback period (years to recover purchase price)
ROI analysis by district and apartment type

Investment Categories
🟢 Excellent (< 20 years): 4.8% of properties
🟡 Good (20-25 years): 10.8% of properties
🟠 Moderate (25-30 years): 32.0% of properties
🔴 Poor (≥ 30 years): 52.4% of properties
🛠️ Technologies

Python 3.9
Data: pandas, numpy
ML: scikit-learn, category_encoders
Visualization: matplotlib, seaborn
APIs: requests

📁 Project Structure
├── Data Collection (APIs)
├── Data Preprocessing
├── Feature Engineering
├── Custom Pipeline Components
├── Model Training & Evaluation
└── Investment Analysis
🎓 Academic Context
Institution: Czech University of Life Sciences Prague
Major: Informatics
Project Type: Bachelor Thesis
🔍 Key Insights

Average payback period varies significantly by district
Larger apartments (3+, 4+) generally have better ROI ratios
Imputing missing furnishing data slightly improves model performance


