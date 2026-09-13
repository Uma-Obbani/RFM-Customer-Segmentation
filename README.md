# RFM Customer Segmentation Analysis

A complete customer lifecycle analytics project that applies Recency, Frequency, and Monetary (RFM) analysis to segment customers into actionable personas for retention, upsell, and marketing strategy decisions.

This project is implemented in a Jupyter Notebook and is designed to help teams understand customer value, behavior, and purchase patterns using a structured, business-friendly workflow.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [Objectives](#objectives)
- [Project Structure](#project-structure)
- [Dataset Requirements](#dataset-requirements)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Run the Notebook](#run-the-notebook)
- [Workflow](#workflow)
- [RFM Methodology](#rfm-methodology)
- [Customer Segments](#customer-segments)
- [Outputs and Visualizations](#outputs-and-visualizations)
- [Key Insights](#key-insights)
- [GitHub Upload Checklist](#github-upload-checklist)
- [License](#license)

---

## Project Overview

Customer segmentation is one of the most valuable tools in lifecycle marketing and CRM strategy. This project analyzes customer purchasing behavior using RFM metrics:

- Recency: how recently a customer made a purchase
- Frequency: how often a customer purchases
- Monetary: how much revenue a customer generates

By combining these three indicators into a scoring model, the analysis segments customers into meaningful personas such as Champions, Loyal Customers, Potential Loyal, Need Attention, At Risk, Lost, and New Customers.

This allows businesses to prioritize marketing efforts and invest resources based on customer value and retention risk.

---

## Business Problem

Modern businesses often face the challenge of understanding customer behavior at scale across millions of transactions. Without segmentation, marketing teams may spend equally on all customers, leading to waste and missed opportunities.

This project addresses the need to:

- identify high-value customers
- spot at-risk customers before churn occurs
- design reactivation strategies for inactive buyers
- prioritize retention efforts for the most profitable segments
- measure revenue concentration across the customer base

---

## Objectives

The main objectives of this project are to:

1. Load and clean transactional customer data.
2. Compute RFM metrics at the customer level.
3. Assign RFM scores from 1 to 5 using quantile-based methods.
4. Build customer segments based on behavioral patterns.
5. Profile segments with revenue, order frequency, and recency data.
6. Produce dashboards and visual insights for business stakeholders.
7. Export the final segmented customer file for downstream use.

---

## Project Structure

```text
RFM Customer Segment Analysis/
├── README.md
├── requirements.txt
├── notebooks/
│   └── rfm.ipynb
├── .venv/                  # local virtual environment (optional, not for GitHub)
├── data/                   # project-level output folder for generated CSVs
│   └── rfm_segments.csv   # exported RFM segment file
└── .gitignore
```

Notes:

- The notebook is saved in the notebooks folder.
- The final exported segment dataset is written to the project-level data directory.
- The raw input dataset should be placed in the data folder outside the notebook folder or in the expected project location, depending on your setup.

---

## Dataset Requirements

The analysis expects a transactional retail dataset with at least these columns:

- Customer ID
- Invoice
- InvoiceDate
- Description
- Quantity
- UnitPrice
- Country
- TotalRevenue

The project uses a cleaned retail dataset named:

- cleaned_online_retail_data.csv

This dataset should be accessible to the notebook in one of the supported locations:

- ./data/cleaned_online_retail_data.csv
- ../data/cleaned_online_retail_data.csv
- project root /cleaned_online_retail_data.csv

If the dataset is not present, the notebook raises a FileNotFoundError and asks the user to update the CSV path.

> Important: The raw dataset is typically not uploaded to GitHub because it may be large. Instead, keep the dataset locally and document the path clearly.

---

## Technologies Used

- Python
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook
- pathlib

---

## Installation

1. Clone the repository:

   git clone <your-github-repository-url>

2. Navigate to the project folder:

   cd "RFM Customer Segment Analysis"

3. Create a virtual environment:

   python3 -m venv .venv

4. Activate the virtual environment:

   - On macOS/Linux:

     source .venv/bin/activate

   - On Windows:

     .venv\Scripts\activate

5. Install dependencies:

   pip install -r requirements.txt

---

## Run the Notebook

Open the notebook in Jupyter:

```bash
jupyter notebook notebooks/rfm.ipynb
```

Or run it in VS Code with the project Python environment selected.

If you want to execute from the terminal without Jupyter, the notebook logic can be reproduced in a Python script as needed.

---

## Workflow

The notebook follows a structured customer segmentation workflow:

1. Data loading
2. Data validation and cleaning
3. Removal of invalid negative revenue values
4. RFM metric calculation
5. RFM score assignment
6. Customer segment classification
7. Segment-level analysis and summary tables
8. Visualization creation
9. Pareto analysis for customer concentration
10. Export final segmentation file

---

## RFM Methodology

The analysis calculates three customer metrics:

### 1. Recency (R)

Recency measures the number of days since the last purchase. Lower values are better because they indicate recent engagement.

### 2. Frequency (F)

Frequency measures how often a customer buys. Higher values reflect stronger buying behavior and deeper engagement.

### 3. Monetary (M)

Monetary measures the total revenue contributed by a customer. Higher values indicate stronger financial contribution.

Each metric is classified into a 1–5 score using quantile-based bucketing. This allows different customer behaviors to be compared on a standard scale.

---

## Customer Segments

The segmentation logic assigns each customer to a segment based on their R and F scores.

### Segment definitions

- Champions
- Loyal Customers
- Potential Loyal
- Need Attention
- At Risk
- Lost
- New Customers

These personas help teams target customers according to behavior, value, and retention risk.

Examples:

- Champions: recent, frequent, high-value customers
- Loyal Customers: stable and engaged customers
- Potential Loyal: customers with decent value potential but room to grow
- Need Attention: moderately recent but lower engagement customers
- At Risk: customers who were active but are declining
- Lost: inactive or low-value customers
- New Customers: first-time buyers who need nurturing

---

## Outputs and Visualizations

The notebook produces several outputs:

- customer count by segment
- total revenue by segment
- boxplots for Recency, Frequency, and Monetary distribution
- Pareto chart for customer revenue concentration
- segment summary tables
- final exported CSV with segment labels

### Exported results

The final file is saved here:

- ../data/rfm_segments.csv

This file contains:

- Customer ID
- Recency
- Frequency
- Monetary
- R_Score
- F_Score
- M_Score
- RFM_Score
- RFM_Label
- Segment

---

## Key Insights

The notebook is designed to answer practical business questions such as:

- Which customers are creating the most revenue?
- Which customers are at the highest risk of churn?
- Which segments should receive retention campaigns?
- Which segments are most suitable for loyalty incentives or upselling?
- How concentrated is revenue among the top customer groups?

The Pareto analysis is especially useful because it highlights how a small share of customers can contribute a large share of total value.

---

## Example Business Actions

Each customer segment can trigger a tailored strategic response:

- Champions: maintain loyalty and offer VIP treatment
- Loyal Customers: reward consistency and deepen engagement
- Potential Loyal: encourage repeat purchases and upselling
- Need Attention: re-engage with win-back campaigns
- At Risk: identify churn risk and launch retention offers
- Lost: reactivation campaigns or reminder messaging
- New Customers: onboarding and conversion nurturing

---

## GitHub Upload Checklist

Before uploading to GitHub, ensure the following:

- [ ] README.md is complete and professional
- [ ] requirements.txt includes all dependencies
- [ ] notebook runs without syntax errors
- [ ] Jupyter output is clean or intentionally kept minimal
- [ ] large raw data files are not committed
- [ ] generated CSV files are excluded if they are not meant to be versioned
- [ ] .gitignore includes .venv and local data directories if needed
- [ ] project structure is organized and easy to follow
- [ ] notebook is saved in the notebooks folder
- [ ] file paths are documented clearly

Example .gitignore entries:

```gitignore
.venv/
__pycache__/
.ipynb_checkpoints/
.DS_Store
```

If you want to keep data files local, do not upload large CSV files unless they are intentionally included.

---

## Recommended GitHub Repository Description

RFM Customer Segmentation Analysis using Python and Jupyter Notebook for customer lifecycle insights, retention strategy, and revenue optimization.

---

## License

This project is intended for educational, analytical, and business use. Add an appropriate license if you plan to publish it publicly on GitHub.

Common choices:

- MIT License
- Apache 2.0
- GPL 3.0

---

## Final Notes

This repository is suitable for:

- portfolio projects
- CRM analytics case studies
- customer value analysis presentations
- retention and loyalty strategy work
- marketing performance research

It is a strong project for GitHub because it combines data analysis, visualization, business storytelling, and practical decision-making.

---

## Summary

This project transforms raw transactional customer data into a strong business intelligence workflow by:

- segmenting customers based on behavior
- ranking them using RFM scoring
- identifying revenue concentration and churn risk
- generating actionable marketing recommendations

It is a polished, presentation-ready analytics project that can be shared on GitHub as a professional data science portfolio piece.
