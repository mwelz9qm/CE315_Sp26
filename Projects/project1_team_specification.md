# CE 315 - Team Project: Applied Machine Learning Design Project

## Overview

**Due Date:** 2/25/2026 
**Total Points:** 100 points  
**Presentation:** 15 minutes 

**Objective:** Apply machine learning techniques to solve a real-world problem of your choosing. You will find your own dataset, perform thorough analysis, build multiple models, and present actionable recommendations based on your findings.

---

## Project Requirements

### 1. Problem Selection & Data (Choose Your Own!)

**You must:**
- Select a **real-world problem** that interests your team
- Find or collect a **real dataset** (minimum 500 samples, 5+ features)
- **Get my approval** by 2/11/2026
- Justify why this problem matters (business/engineering/social impact)

**Acceptable Data Sources:**
- Kaggle datasets
- UCI Machine Learning Repository
- Government databases (data.gov, census, etc.)
- Industry APIs (Twitter, weather, financial, etc.)
- Your own collected data (surveys, sensors, web scraping)
- Academic datasets

**Unacceptable:**
- Toy datasets (Iris, basic MNIST)
- Datasets used in class (Titanic, Student Performance, Bike Sharing)
- Datasets with <500 samples or <5 features
- Proprietary data you don't have permission to use

---

### 2. Technical Requirements (Must Include ALL)

#### A. Data Analysis & Preparation
-  Exploratory Data Analysis (EDA) with visualizations
-  Data cleaning and handling missing values
-  Feature engineering (create at least 2 new meaningful features)
-  Train/validation/test split strategy

#### B. Model Building (Minimum 4 Models)
You must implement at least **4 different models** including:
- **At least 1 linear model** (Linear/Logistic Regression with regularization)
- **At least 1 tree-based model** (Decision Tree or Random Forest)
- **At least 1 ensemble method** (Bagging, Random Forest, or Boosting)
- **1 additional model** of your choice (we'll cover more in class or you can explore on your own)

#### C. Model Evaluation & Comparison
- Cross-validation (proper use of CV for all models)
- Hyperparameter tuning (GridSearchCV for at least 2 models)
- Performance metrics appropriate for your problem
- Comparison table of all models

#### D. Uncertainty Quantification
- Bootstrap confidence intervals on key metrics
- Feature importance analysis (for applicable models)
- Discussion of model limitations and uncertainty

#### E. Engineering Design Decisions
- Justify model selection for deployment
- Discuss trade-offs (accuracy vs speed vs interpretability)
- Address practical constraints (computational cost, data requirements)
- Recommend next steps and improvements

---

## Deliverables 

### 1. Project Proposal (Due: 2/13/26)
**Submission:** 1-page PDF per team  
**Points:** 10 points  

**Must include:**
- Problem statement and motivation
- Dataset description (source, size, features)
- Preliminary research question
- Expected challenges
- Team member names and proposed roles

**Purpose:** Get feedback early, ensure project scope is appropriate

---

### 2. Jupyter Notebook (Due: Presentation Day)
**Submission:** .ipynb file per team  
**Points:** 40 points  

**Structure:**
```
1. Introduction
   - Problem statement
   - Dataset description
   - Project goals

2. Data Loading & Exploration
   - Load and display data
   - Summary statistics
   - Visualizations (5+ plots)
   - Key insights from EDA

3. Data Preparation
   - Handling missing data
   - Feature engineering
   - Train/test split

4. Model 1: [Name]
   - Implementation
   - Cross-validation
   - Results

5. Model 2: [Name]
   - Implementation
   - Hyperparameter tuning
   - Results

6. Model 3: [Name]
   - Implementation
   - Results

7. Model 4: [Name]
   - Implementation
   - Results

8. Model Comparison
   - Performance comparison table
   - Bootstrap confidence intervals
   - Visualizations comparing models
   - Statistical significance tests

9. Feature Importance & Interpretation
   - Feature importance plots
   - Insights about what drives predictions

10. Final Recommendations
    - Best model and why
    - Limitations and uncertainties
    - Practical deployment considerations
    - Future work

11. Conclusion
```

**Code Quality Requirements:**
- All cells run without errors
- Clear comments explaining code
- Professional markdown explanations
- Visualizations have labels and titles
- Results are reproducible (set random seeds)

---

### 3. Individual Technical Report (Due: Presentation Day)
**Submission:** 2-3 page PDF per student  
**Points:** 20 points  

**This is INDIVIDUAL work. No collaboration.**

**Required Sections:**

**A. Your Contribution**
- Specifically what you did on this project
- Which models you implemented
- Which analyses you performed
- Which visualizations you created
- Challenges you faced and how you solved them

**B. Technical Deep Dive**
Choose ONE of your models and explain IN DETAIL:
- Why this model is appropriate for the problem
- How the model works (algorithm explanation)
- Hyperparameters you tuned and why
- Results and interpretation
- Comparison to other models

**C. Reflection**
- What you learned from this project
- How you would improve the project given more time
- How ML could be applied to other problems in your field
- What was the hardest part and why


---

### 4. Team Presentation (about 15 minutes)
**Points:** 25 points (10 team + 15 individual)  

**Presentation Structure:**
1. **Problem & Motivation**
   - What problem are you solving?
   - Why does it matter?

2. **Data & EDA**
   - Dataset description
   - Key patterns discovered (2-3 visualizations)

3. **Approach**
   - Models you tried
   - Overall methodology

4. **Results**
   - Performance comparison
   - Best model and why
   - Key insights from feature importance

5. **Engineering Design**
   - Deployment recommendations
   - Trade-offs considered
   - Limitations and uncertainty

6. **Conclusions**
   - Main takeaways
   - Future work

7. **Q&A**
   - Be prepared for technical questions!

**Individual Accountability in Presentation:**
- **Each team member must present a section**
- **Each member will be asked individual questions**
- You will be graded on YOUR portion and YOUR answers

---

### 5. Peer Evaluation (Due: 2 days after presentation)
**Submission:** Confidential form  
**Impact:** Can adjust individual grades 
**Points:** 5

**You will rate each teammate (including yourself) on:**
- Quality of technical contributions
- Effort and engagement
- Communication and collaboration
- Meeting attendance and deadlines

**Scale:** 1-5 (1=poor, 5=excellent)

**This is confidential and taken seriously.**

---




---

## Timeline & Milestones

### Week 1
- Form teams, brainstorm ideas
- Find dataset, explore feasibility
- **Submit proposal** (10 points)
- Instructor approves or requests changes

### Week 2
- EDA and data preparation
- Implement first 2 models
- Implement remaining models, start comparisons
- Office hours check-in

### Week 3
- Model comparison, bootstrap analysis, feature importance
- Finalize notebook, create presentation, write individual reports
- **PRESENTATIONS** + submit all deliverables

---

## Some Suggested Problem Domains

To help you get started, here are domains with good datasets:

### Engineering Applications
- **Energy consumption prediction** (buildings, cities)
- **Equipment failure prediction** (sensors, maintenance)
- **Quality control** (manufacturing defects)
- **Traffic flow prediction** (transportation)
- **Structural health monitoring** (bridges, buildings)

### Business Applications
- **Customer churn prediction** (telecom, subscription)
- **Sales forecasting** (retail, e-commerce)
- **Credit risk assessment** (lending)
- **Product recommendation** (e-commerce)
- **Fraud detection** (financial transactions)

### Healthcare Applications
- **Disease diagnosis** (medical records)
- **Hospital readmission prediction**
- **Drug efficacy prediction**
- **Patient risk stratification**

### Environmental Applications
- **Air quality prediction** (pollution, sensors)
- **Weather prediction** (meteorological data)
- **Wildfire risk assessment**
- **Species classification** (ecological surveys)

### Social Applications
- **Housing price prediction** (real estate)
- **Crime prediction** (public safety)
- **Student performance** (education - but NOT the dataset from class!)
- **Social media sentiment** (text analysis)


