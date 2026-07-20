# Developer Guide

## Steam Review Research and Insights Tool

Author: Marit Sullivan

---

# Overview

The Steam Review Research and Insights Tool was developed as my final project for HCI 5840 course at Iowa State Univeristy. The application assists video game User Research and Insights teams by collecting and analyzing Steam player reviews. The system downloads reviews using the Steam Reviews API, categorizes feedback into gameplay themes, performs statistical analyses, generates visualizations, and creates AI-generated summaries using Ollama.

The project is separated into two major workflows:

1. Data Collection
2. Data Analysis

Separating these workflows allows review collection to occur independently of analysis. This design supports batch data collection and enables users to analyze previously collected review datasets without repeatedly accessing the Steam API.

---

# Current Implementation

Version 1 currently implements:

- Steam review scraping
- CSV export
- Data cleaning
- Keyword-based review categorization
- Sentiment analysis
- Statistical analysis
- Correlation analysis
- Boxplots
- Histograms
- Category frequency visualizations
- AI-generated summaries
- Executive Summary

Not currently implemented:

- Interactive web interface
- Real-time Steam API integration
- Multi-game comparison
- Machine learning classification

---

# Project Structure

```

Marit_Project/

README.md User Guide

steam_scraper.py Downloads Steam reviews

review_analysis.ipynb Performs analysis

requirements.txt

LICENSE

docs/
Developer_Guide.md

images/

```

---

# Developer Setup

The developer should first follow the installation instructions in the README.

Additional developer requirements include:

- Python 3.13.11
- Jupyter Notebook
- Ollama (optional)
- Git

---

# System Architecture

The application consists of two different stages - Data collection and Data Analysis.

## Stage 1 – Data Collection

Module:

steam_scraper.py

Responsibilities:

- Connect to Steam Reviews API
- Download reviews
- Handle pagination
- Clean review text
- Export CSV

Output:

reviews_<appid>.csv

---

## Stage 2 – Data Analysis

Module:

review_analysis.ipynb

Responsibilities:

- Load CSV
- Calculate sentiment
- Categorize reviews
- Perform statistical analysis
- Generate visualizations
- Generate AI summaries
- Produce Executive Summary

---

# Application Workflow

User executes:

steam_scraper.py

↓

Steam Reviews API

↓

CSV file created

↓

review_analysis.ipynb

↓

Load DataFrame

↓

Review Categorization

↓

Statistical Analysis

↓

Visualizations

↓

AI Summary

↓

Executive Summary

---

# Major Functions

## categorize_review()

Uses keyword matching to assign one or more gameplay categories to each review.

Returns:

- Usability Issues
- Story / Campaign
- Community & Social
- SBMM / Matchmaking
- Technical Requirements
- Monetization & Value
- Competitive Analysis
- AI Generated Content
- Game Reception

---

## analyze_boxplot()

Creates boxplots for comparing review metrics across categories.

---

## ai_summary()

Sends prompts to Ollama to summarize statistical analyses and player feedback.

---

## generate_executive_summary()

Produces the final project summary by combining descriptive statistics, category frequencies, helpful vote analysis, and AI-generated insights.

---

# Known Issues

Minor

- Keyword categorization may miss uncommon wording.
- AI summaries depend on Ollama availability.

Major

- AI summaries will fail if Ollama is not running.
- Only one Steam game can be analyzed at a time.

---

# Computational Limitations

The project currently performs keyword matching sequentially.

For very large datasets (100,000+ reviews), runtime may increase significantly.

Future versions should investigate:

- spaCy
- BERTopic
- Sentence Transformers
- GPU acceleration

---

# Future Work

Potential improvements include:

- Flask or Streamlit web application
- Multi-game comparison
- Automatic topic modeling
- Interactive dashboards
- Export to PDF
- Export to Excel
- Machine learning classification
- Cloud deployment
- Web page application

---

# Ongoing Development

Future developers should:

- Update keyword lists as gameplay terminology evolves.
- Maintain compatibility with Steam API changes.
- Test AI summaries whenever Ollama models are updated.
- Preserve modular separation between scraping and analysis.
- Implement statistical and AI comparison accross different video games in the First Person Shooter Genre
- Implement statistical and AI comparison across different video game Genres. 