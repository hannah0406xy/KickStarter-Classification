## 📋 Overview

This project employs machine learning techniques to predict Kickstarter campaign success and understand key factors driving positive outcomes. Using classification and clustering approaches, the analysis provides actionable insights for both project creators and platform managers to optimize campaign performance.

## 🎯 Project Goals

- Develop a classification model to predict campaign success at launch time
- Identify key features that influence project outcomes
- Discover natural groupings of projects with shared characteristics
- Provide data-driven recommendations for improving success rates

## 📊 Dataset

The analysis uses a dataset of Kickstarter projects with:
- Project metadata (categories, countries, etc.)
- Financial information (goal amounts)
- Media elements (video presence, featured images)
- Temporal features (launch duration, creation-to-launch time)
- Text content (name length, blurb length)

## 🔍 Methodology

### Classification Analysis

**Feature Engineering:**
- Currency conversion to USD
- Log transformation for skewed financial distributions
- One-hot encoding for categorical variables
- Temporal feature creation (launch duration, creation-to-launch time)

**Feature Selection:**
- Project category (Cramer's V = 0.594)
- Goal amount (p = 0.0007 in ANOVA testing)
- Media presence (video: Cramer's V = 0.136, images: Cramer's V = 0.158)
- Project description metrics (name/blurb length)
- Low multicollinearity verified across selected features

**Model Development:**
- Evaluated Random Forest, Logistic Regression, and Gradient Boosting
- Optimized with grid search (learning rate: 0.1, max_depth: 5, n_estimators: 200)
- Final Gradient Boosting model achieved:
  - 80% overall accuracy
  - 85% recall for successful campaigns
  - 81% precision for successful campaigns

### Clustering Analysis

**Feature Selection:**
- Financial metrics (converted to USD)
- Media presence indicators
- Promotional features
- Funding ratios
- Log-transformed financial variables

**Approach:**
- K-Means algorithm with k=5 clusters (optimized via silhouette score)
- Revealed distinct project archetypes with varying success patterns

## 🔑 Key Findings

### Identified Project Clusters:

1. **Standard Success Track (32.30% of projects)**
   - Moderate goals ($7,500 median)
   - Strong video presence
   - No special platform features required

2. **Premium Track (13.37%)**
   - 91.21% success rate
   - Comprehensive platform utilization
   - Staff recognition

3. **Risk Zone (25.05%)**
   - Overambitious goals ($10,000 median)
   - Insufficient platform support
   - Critical failure patterns

4. **Entry Level (25.94%)**
   - Modest goals ($652 median)
   - Proven pathway for new creators

5. **Media Excellence (3.33%)**
   - Perfect success rate
   - Comprehensive media strategy

## 💡 Recommendations

### For Project Creators:

- Start with modest goals under $1,000 to build track record
- Gradually progress to higher targets
- Implement comprehensive media presence for projects over $5,000
- Seek staff recognition for higher-goal projects
- Utilize platform features effectively

### For Platform Management:

- Implement automated risk assessment system based on classification model
- Provide enhanced support for projects showing risk factors
- Develop graduated approach to project goals and feature requirements
- Guide creators through proven pathways from entry-level to premium projects

## 📈 Future Work

- Real-time prediction system integration
- Enhanced feature engineering with NLP on project descriptions
- Time series analysis of campaign performance
- Development of a web application for project success assessment

## 👥 Contributors

- Xinyi Wang
