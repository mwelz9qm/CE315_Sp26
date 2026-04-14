# CE 315 — Final Project: Uncertainty Quantification in Neural Networks

## Overview

**Total Points:** 100 points  

**Progress Update Due:** 4/20/2026 

**All Final Deliverables Due:** 4/29/2026

**Presentations:** 4/29/206 during exam slot, 20–25 minutes per team

**Objective:** Implement and evaluate a neural network uncertainty quantification method on a nuclear engineering benchmark problem from pyMAISE. This project is a collaboration with the University of Michigan's AIMS lab and builds directly on the techniques introduced by Dr. Radaideh and Leo Tunkle.

Each team has been assigned one of three approaches. All three address the same fundamental question — "How confident is this prediction?" — but through different mechanisms.

---

## Project Assignments

### Project 1: MC Dropout

Implement Monte Carlo Dropout as a lightweight approach to uncertainty quantification. Train a single neural network with dropout layers, then keep dropout active during prediction and perform multiple stochastic forward passes (20–100) to obtain a predictive distribution.

**Tasks:**
- Build a neural network with dropout layers using TensorFlow/Keras
- Enable dropout during inference (the `training=True` flag)
- Generate predictions with uncertainty (mean, standard deviation, 95% confidence intervals) from repeated forward passes
- Evaluate on a pyMAISE benchmark (CHF for single-output, MIT reactor for multi-output)
- Assess calibration: do ~95% of true values fall within the 95% CI?

### Project 2: Deep Ensembles


Implement Deep Ensembles by training multiple independently initialized neural networks. Uncertainty comes from the disagreement between ensemble members.

**Tasks:**
- Train M independent neural networks (5–10 members) with identical architectures but different random seeds
- Aggregate predictions to compute mean, variance, and 95% confidence intervals
- Optionally extend each member to predict both mean and variance (heteroscedastic regression with NLL loss)
- Decompose uncertainty into epistemic (between-model disagreement) and aleatoric (within-model variance, if modeled)
- Evaluate on a pyMAISE benchmark (CHF for single-output, MIT reactor for multi-output)

### Project 3: Variance Reduction and Bias Mitigation


Investigate where prediction uncertainty comes from by training diverse models and analyzing their agreement and disagreement patterns. Decompose bias into three potential sources.

**Tasks:**
- Train diverse models varying architecture, hyperparameters, and initialization (model bias)
- Generate multiple training sets using different sampling strategies: bootstrapping, Latin Hypercube, stratified sampling (sampling bias)
- Swap train/test sets systematically via k-fold cross-validation and assess consistency (data bias)
- Aggregate predictions to compute mean, variance, and 95% confidence intervals
- Report whether bias is detected and identify its source (model, sampling, or data)
- Evaluate on a pyMAISE benchmark (CHF for single-output, MIT reactor for multi-output)

---

## Deliverables

### 1. Progress Update (Due: 4/20)

**Points:** 7 points  
**Submission:** Brief report

Each team gives a short informal update covering:
- What you've completed so far
- Preliminary results (even if rough)
- What's left to do
- Any blockers or questions

This is a checkpoint, not a polished . The goal is to make sure every team is on track and to surface problems early enough to fix them.

---

### 2. Code Submission (Due: 4/29)

**Points:** 30 points  
**Submission:** Jupyter notebook (.ipynb) or Python project (uv project with scripts), one per team

**Requirements:**
- All code runs without errors from top to bottom in a fresh environment
- Clear comments explaining what each section does and why
- Markdown cells (if notebook) or README (if scripts) explaining the approach, decisions made, and results
- Reproducible: random seeds set, data loading automated
- Organized: logical flow from data loading → model training → uncertainty quantification → evaluation → visualization

**What we're looking for:**
- Correct implementation of the assigned UQ method
- Proper use of a pyMAISE benchmark dataset
- Uncertainty estimates (mean, std, 95% CI) computed and visualized
- At least one parity plot showing predictions vs. true values with uncertainty bands
- Metrics table (R², RMSE, MAE) for the model(s)
- Calibration assessment: what fraction of true values falls within the stated confidence intervals?

---

### 3. Technical Paper (Due: 4/29)

**Points:** 25 points  
**Submission:** PDF, 6–10 pages (including figures), one per team  
**Every team member must contribute to writing. Clearly indicate who wrote which sections.**

**Required sections:**

**Introduction**  
What problem are you solving? Why does uncertainty quantification matter for this application? Brief background on your assigned method.

**Methods**  
Describe your UQ approach in enough detail that a classmate working on a different project could understand it. Include network architecture, hyperparameters, training procedure, and how uncertainty estimates are computed. Explain design decisions — why did you choose this architecture, this number of ensemble members, this dropout rate, etc.?

**Results**  
Present your findings with clear visualizations. At minimum: predictions vs. true values with uncertainty bands, metrics table, and calibration assessment. Compare performance with and without UQ if applicable.

**Discussion**  
Interpret your results. Where does the model perform well? Where does it struggle? Is the uncertainty well-calibrated? What are the limitations of your approach? How would you improve it given more time?

**Conclusion**  
Key takeaways. Is this UQ method practical for the application you tested it on?

**Individual Contributions**  
A brief section listing who did what. Be specific and honest.

---

### 4. Presentation (During Final Exam Period)

**Points:** 30 points  
**Duration:** 20–25 minutes + 5 minutes Q&A  

**Every team member must present a substantial section and will be graded individually on their portion.**

**Grading criteria:**

- Technical accuracy of the presentation
- Quality of visualizations and results
- Clear explanation of the UQ method
- Honest assessment of limitations
- Clarity and confidence in presenting your section
- Ability to answer technical questions about the project
- Demonstrated understanding of the material (not just your section — you should understand the whole project)

**Be prepared for questions.** I will ask questions and Michigan collaborators may also attend.

---

### 5. Peer Evaluation (Due: 4/29)

**Points:** 8 points  
**Submission:** Confidential form, submitted individually

Rate each teammate (including yourself) on the **final project only**:

- Quality of technical contributions (code, analysis, writing)
- Effort and engagement throughout the project
- Communication and collaboration
- Meeting deadlines and following through on commitments

Scale: 1–5 (1 = minimal contribution, 5 = exceptional contribution)

Include a brief written comment for each teammate. This is confidential and will be used to adjust individual grades if the team's contributions were significantly unequal.



---

## Point Summary

| Component | Points |
|---|---|
| Progress update | 7 |
| Code submission | 30 |
| Technical paper | 25 |
| Presentation score | 30 |
| Peer evaluation | 8 |

| **Total** | **100 ** |


---

## Resources

- **pyMAISE documentation:** https://pymaise.readthedocs.io
- **pyMAISE benchmarks:** https://pymaise.readthedocs.io/en/latest/benchmarks.html
- **Leo's UQ notebook** (variational FNN + deep ensemble on CHF data)
- **Course UQ notebook** (GP vs. neural network uncertainty)
- **Course neural network uncertainty review** (MC Dropout, mean-variance networks, deep ensembles)

---

## A Note on Collaboration

Each team works independently on their assigned method. However, since two teams share the Variance Reduction and Bias Mitigation
 project, those teams should work completely independently — different implementations, different design decisions, potentially different benchmark problems. The presentations will be more interesting if the two teams took different approaches and can compare.

Cross-team discussion about general concepts (e.g., "how does pyMAISE load data?") is fine. Sharing code or results between teams is not.