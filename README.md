Visit: https://reforest-ai.onrender.com/

# ReForest AI

## An Intelligent Machine Learning System for Forest Degradation Analysis, Carbon Emission Assessment, and Reforestation Prioritization

## Overview

**ReForest AI** is a machine learning-based web application designed to analyse forest degradation, assess carbon emissions, explore future forest-loss scenarios, and prioritise reforestation efforts across India.

The project uses historical forest and carbon-related datasets to identify forest-loss patterns, evaluate environmental indicators, estimate future scenarios, and generate priority rankings to support data-driven reforestation planning.

## Key Features

- **Forest Loss Analysis:** Analyse historical forest-cover loss across India at country, state, and district levels.
- **Carbon Emission Assessment:** Examine carbon emissions and related environmental indicators associated with forest loss.
- **Historical Analysis:** Visualise annual and cumulative forest loss, carbon emissions, and state-wise patterns.
- **Present Forest Status:** Review remaining forest cover, net forest loss, annual loss, and the most affected states.
- **Future Scenario Analysis:** Compare Business-as-Usual and Reforestation scenarios for 2021–2030.
- **Machine Learning Models:** Implement multiple regression algorithms to estimate forest loss and evaluate model performance.
- **AI-Based Prioritization:** Apply fuzzy logic to classify regions into Critical, High, Moderate, and Low priority categories.
- **Interactive Dashboard:** Present analytical results through a web-based interface.

## Machine Learning Pipeline

The project implements the following machine learning algorithms:

1. Random Forest Regression
2. XGBoost Regression
3. CatBoost Regression
4. LightGBM Regression
5. Ridge Regression
6. AdaBoost Regression

### Model Evaluation

The models are evaluated using:

- R² Score
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Weighted Absolute Percentage Error (WAPE)
- Leave-One-Out Cross-Validation (LOOCV)

Feature importance is also analysed where supported by the model.

### Feature Engineering

The pipeline generates features including:

- Total and average annual forest loss
- Maximum, minimum, and standard deviation of annual loss
- Remaining forest area and forest-cover ratio
- Forest-cover change
- Deforestation acceleration and trend
- Carbon emissions and carbon intensity
- Net carbon flux
- Biomass density
- Forest vulnerability indicators

### Reforestation Prioritization

A fuzzy logic-based priority engine evaluates regions using factors such as historical forest loss, remaining forest ratio, and carbon intensity.

Regions are classified into four priority levels:

- Critical
- High
- Moderate
- Low

The resulting scores are intended to support reforestation planning and decision-making.

## Future Scenario Analysis

ReForest AI compares two scenarios for the period 2021–2030:

**Business-as-Usual (BAU):** Estimates future forest loss using historical trends, recent trends, and average loss patterns.

**Reforestation Scenario:** Estimates a gradual reduction in forest loss using assumed annual reduction rates.

The system compares potential forest-loss avoidance and carbon savings between the scenarios. These are scenario-based estimates, not guaranteed future outcomes.

## Dataset

The project uses the Kaggle dataset:

**Deforestation Cover India - 2000–2020**

The dataset consists of six Excel files covering:

- Country-level tree-cover loss
- State-level tree-cover loss
- District-level tree-cover loss
- Country-level carbon data
- State-level carbon data
- District-level carbon data

A 30% tree-cover density threshold is applied in the analysis.

## Technology Stack

| Component | Technologies |
|---|---|
| Programming Language | Python |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn, XGBoost, CatBoost, LightGBM |
| Backend | Flask |
| Frontend | React, Vite, Tailwind CSS |
| Data Visualization | Web-based dashboard visualizations |
| Model Storage | Joblib |
| Deployment | Render |
| Containerization | Docker, Docker Compose |

## Project Structure

```text
ReForest-AI/
│
├── Dataset/
│   ├── country_tree_loss.xlsx
│   ├── state_tree_loss.xlsx
│   ├── district_tree_loss.xlsx
│   ├── country_carbon.xlsx
│   ├── state_carbon.xlsx
│   └── district_carbon.xlsx
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── ml_outputs/
├── models/
├── static/
├── templates/
│
├── app.py
├── ml_pipeline.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
└── Procfile
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd ReForest-AI
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows**
```bash
venv\Scripts\activate
```

**Linux / macOS**
```bash
source venv/bin/activate
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the Dataset

Place all six Excel dataset files inside the `Dataset/` directory, using the filenames expected by the pipeline.

### 5. Run the Machine Learning Pipeline

```bash
python ml_pipeline.py
```

This executes the data processing, feature engineering, model training, evaluation, fuzzy prioritization, and scenario analysis pipeline.

### 6. Run the Backend

```bash
python app.py
```

### 7. Run the Frontend

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

The frontend development server will display the local URL in the terminal.

## Deployment

The application is deployed using **Render**. Docker configuration files are also included to support containerized deployment.

Add your live application URL here:

**Live Demo:** `<YOUR_RENDER_URL>`

## Future Scope

- Integrate more recent and higher-resolution forest-cover datasets.
- Explore the proposed India Forest Cover and Reforestation 1987–2036 dataset.
- Improve forecasting methods using additional temporal and environmental variables.
- Incorporate satellite imagery and remote-sensing indicators.
- Explore geographic mapping for more detailed regional analysis.
- Improve prioritization using additional ecological and socioeconomic factors.
- Validate model outputs and priority recommendations against independent data and field observations.
