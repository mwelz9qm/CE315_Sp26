# CE 315 — Project 1 Extension: Model Expansion & Improvement

## Overview


**Total Points:** 60 points  
**Due:** Notebook and Short Class Update

**Objective:** Return to your Project 1 work and make it meaningfully better. You will add at least one new model (including a neural network), fix weaknesses in your original submission, and prepare your project to serve as the foundation for upcoming work with the pyMAISE framework.

---

## Why Are We Doing This?

Your Project 1 was a first pass. Every team made choices under time pressure — some pipelines had data leakage, some models were left at default hyperparameters, some EDA was thin, some feature engineering was surface-level. That's normal for a first attempt.

In two weeks, collaborators from the University of Michigan will be working with you on more advanced techniques (Gaussian processes, Bayesian neural networks, uncertainty quantification). **Your Project 1 notebook is the foundation for that work.** The cleaner and stronger it is now, the more you'll get out of those sessions.

This extension is your chance to turn a good first draft into a polished, well-understood project.

---

## Requirements

### 1. Add a Neural Network (Required — All Teams)

**Points:** 10 points

Build, tune, and evaluate a neural network on your dataset using sklearn's `MLPClassifier` or `MLPRegressor`.

You must:

-  Use a `Pipeline` with `StandardScaler` (no exceptions — explain why in a markdown cell)
-  Try at least **3 different architectures** (vary width, depth, or both) and report results for each
-  Use cross-validation on your training set to select the best architecture
-  Evaluate your chosen architecture on the held-out test set
-  Add the neural network to your existing model comparison table and visualization
-  Include a brief markdown discussion: How does the neural network compare to your other models? Is the added complexity worth it for your problem?


---

### 2. Targeted Improvements (Pick 3 — Team Choice)

**Points:** 18 points (6 points each)

Every project has different weaknesses. Choose **3 improvements** from the menu below that address real gaps in your Project 1 work. You may not pick something your project already does well — the point is to fix what's lacking.

**For each improvement you select**, your notebook must include:
- A markdown cell explaining **what was wrong or missing before** and **what you changed**
- The actual implementation
- Evidence that the improvement matters (a before/after comparison, a metric, a visualization — something concrete)

#### Examples of Possible Improvements

**A. Pipeline & Methodology Fixes**
- **A1: Fix data leakage.** If your original notebook scaled or encoded data before splitting, or used test data during development, restructure your workflow using `Pipeline` and `ColumnTransformer` so that all preprocessing is fit only on training data.
- **A2: Proper hyperparameter tuning.** Run `GridSearchCV` or `RandomizedSearchCV` on at least 2 models that were previously left at defaults. Report best parameters and the CV score improvement over defaults.
- **A3: Improve your train/test/CV strategy.** If your original project used a simple train/test split without cross-validation for model selection, implement 5-fold CV across all your models. If your data has a time component, implement time-based splitting instead of random splitting.

**B. Feature Engineering & Data Quality**
- **B1: Create 3+ new domain-informed features** that you didn't have before. Show their correlation with the target and whether they improve model performance (before/after comparison with at least one model).
- **B2: Improve missing data handling.** If you used simple strategies (drop all rows, fill everything with the mean), implement context-appropriate imputation. Justify your choices based on *why* data is missing.
- **B3: Address class imbalance or skewed targets.** If your classification target is imbalanced, implement and compare strategies (class weights, Synthetic Minority Over-sampling Technique(SMOTE), threshold tuning). If your regression target is skewed, try a log transform and show the effect on residuals.

**C. Evaluation & Interpretation**
- **C1: Add learning curves.** For at least 2 models, generate learning curves (performance vs. training set size). Diagnose whether your models are in a high-bias or high-variance regime and discuss what that means for your problem.
- **C2: Improve your feature importance analysis.** Go beyond a single bar chart. Compare feature importances across at least 2 different methods (e.g., Random Forest importances vs. permutation importance vs. linear model coefficients). Discuss where they agree and disagree.
- **C3: Error analysis.** Identify the samples your best model gets most wrong. Are there patterns? Visualize the worst predictions and discuss what makes them hard. For classification: show the most confident wrong predictions. For regression: plot residuals and identify structure.

**D. Additional Model**
- **D1: Add an SVM** (with proper scaling in a pipeline). Compare linear vs. RBF kernels. Tune C and gamma via grid search.
- **D2: Add a gradient boosting model** (e.g., `GradientBoostingClassifier`/`Regressor` or XGBoost if you want to install it). Tune key hyperparameters (learning rate, n_estimators, max_depth).


---

### 3. Individual Contribution Report

**Points:** 10 points  
**Submission:** 1–2 page PDF, submitted individually  
**This is individual work. No collaboration.**

This is not a rehash of your Project 1 individual report. This report covers **only the extension work.**

**Required sections:**

**A. What You Did**

Be specific. "I worked on the neural network" is not enough. I'm looking for things like: "I implemented the neural network pipeline, ran the architecture search over (32,), (64, 32), and (128, 64, 32), and wrote the comparison discussion. I also implemented improvement C3 (error analysis), where I identified that our model consistently underpredicts sale prices for houses with recently remodeled kitchens."

If you pair-programmed or collaborated closely on a section, say so honestly and describe your specific role.

**B. Technical Explanation**

Choose **one or both(if they apply)** of the following prompts:

1. **Neural network architecture:** Explain what hidden layers and neurons are, what the activation function does, and why your best architecture outperformed (or underperformed) your other models on this dataset. Be specific to your data — don't just give textbook definitions.

2. **One of your chosen improvements:** Explain the technical concept behind the improvement you chose, why it matters for your specific dataset, and what changed in your results. For example, if you fixed data leakage, explain what data leakage is, where it was happening in your pipeline, and how the corrected results differed.

**C. Honest Assessment**

- What is the single biggest remaining weakness in your project?
- If you had another two weeks, what would you do next?
- Is your best model good enough to actually deploy for your problem? Why or why not?

---

### 4. Peer Evaluation

**Points:** 5 points  
**Submission:** Confidential form

Same format as Project 1. Rate each teammate (including yourself) on the **extension work only**:

- Quality of technical contributions
- Effort and engagement
- Communication and collaboration
- Meeting deadlines

Scale: 1–5. This is confidential and will be used to adjust individual grades if needed.

---

### 5. (Short) Presentation
**Points:** 10 points  

Each team member should spend just a couple minutes (2-3 minues per person) describing their work on the extention/improvements to the class.


## Updated Notebook Requirements

Your final submitted notebook should be a **single, clean notebook** that integrates the extension work into your Project 1 notebook — not a separate file. The reader should be able to go through it start to finish and see a coherent project.

**Specifically:**

- The neural network appears as a new model section alongside your original models
- Your model comparison table and chart include all models (original + new)
- Improvements are integrated where they logically belong (e.g., pipeline fixes go in the Data Preparation section, not tacked on at the end)
- A new markdown section titled **"Project Extension Notes"** at the end briefly lists which 3 improvements you chose and where in the notebook to find them
- All cells run without errors, top to bottom, in a fresh kernel

---

## Point Summary

| Component | Points |
|---|---|
| Neural network (pipeline, architecture search, comparison, discussion) | 10 |
| Improvement 1 (with before/after evidence) | 6 |
| Improvement 2 (with before/after evidence) | 6 |
| Improvement 3 (with before/after evidence) | 6 |
| Notebook integration and quality (runs clean, well-organized, markdown) | 7 |
| Individual contribution report | 10 |
| Peer evaluation | 5 |
| Short Presentation | 10 |
| **Total** | **60** |

---


## A Note on What's Up Next

After this extension, your project notebook will have: thorough EDA, clean pipelines, multiple well-tuned models including a neural network, honest evaluation with cross-validation, feature importance analysis, and a discussion of limitations.

The University of Michigan collaborators will then introduce you to techniques that address a fundamental question your current models can't answer: **"How confident should I be in this prediction?"** Your cleaned-up project will be the testbed for those methods. The better your foundation, the more you'll get out of those sessions.
