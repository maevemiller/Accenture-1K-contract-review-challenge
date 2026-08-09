# Contract Review Challenge

**Company / Org:** Accenture  
**Challenge Advisor:** Adarsh Ravikumar, adarsh.ravikumar@accenture.com  
**Program:** Break Through Tech AI Studio - Fall 2026  

---

## 🏢 About Accenture
Accenture is a leading global professional services company that provides a broad range of services and solutions in strategy, consulting, technology, and operations.

---

## 🎯 The Challenge
### Project Summary
In this project, you will use real-world commercial contracts from the CUAD dataset (510 contracts, 41 expert-annotated clause categories) and NLP techniques to build a pipeline that automatically detects key clauses, flags them as Low/Medium/High risk, and rolls these up into a contract-level triage score. To keep the project achievable on free-tier compute within the program timeline, the team will **fine-tune a pre-trained lightweight transformer encoder (e.g., DistilRoBERTa)** rather than training a model from scratch, and will **focus initial clause detection on the 10 most impactful clause categories**, with full coverage of all 41 CUAD categories as a stretch goal. Risk flags will be produced by an explainable rule-based scoring layer built on top of the detected clauses. This will help our company address the bottleneck legal and procurement teams face when manually reviewing tens of thousands of contracts a year to find the small number of clauses that carry meaningful risk, enabling reviewers to prioritize which contracts to open first.

### Success Criteria
Success has two tracks:
- For clause detection: per-category precision/recall/F1 clearly beating the baseline (accuracy is misleading under CUAD's imbalance), evaluated on the 10 focus categories, with error analysis on where the model struggles.
- For risk scoring: since there are no ground-truth labels, success means strong Spearman correlation and bucket agreement between the model's risk rankings and the advisor's hand-ranked clauses, plus a sensitivity analysis showing the High/Medium boundary is stable.

Overall, a successful December outcome is a working end-to-end pipeline producing risk-scored clause registers the advisor finds plausible and useful, a clean documented repo, and a final report covering results, limitations, and estimated reviewer time saved — an auditable triage tool the advisor would actually trust, not a black box.

### Stretch Goals
Stretch goals include expanding clause detection from the 10 focus categories to the full 41 CUAD categories, span extraction, a trained risk model benchmarked against the rule-based baseline, LLM-generated clause explanations, a Streamlit/Gradio demo, and an active-learning loop using advisor/model disagreements. These extend modeling or usability without affecting core deliverables.

### Project Milestones
Use these milestones to guide your work. Your team will create a GitHub Projects board to track tasks within each milestone.
| Month | Milestone | Key Activities |
|-------|-----------|----------------|
| **September** | Data Foundations & Baseline | Clean and split the CUAD data, run EDA on class imbalance, select the 10 highest-impact clause categories for initial focus, build a chunking strategy, and establish a TF-IDF/keyword baseline with per-category metrics. |
| **October** | Lightweight Transformer Fine-Tuning | Fine-tune a pre-trained lightweight transformer encoder (e.g., DistilRoBERTa) for multi-label clause classification on the 10 focus categories, address class imbalance, evaluate with per-category precision/recall/F1, and conduct error analysis. |
| **November** | Risk Scoring & Pipeline Integration | Build and calibrate the four-signal risk-scoring layer, assemble the end-to-end pipeline, and validate risk rankings against advisor-labeled examples. |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset
**Name and Source:** CUAD Dataset (Contract Understanding Atticus Dataset)  
**Format:** JSON, Raw Text/PDF  
**Size:** under 1gb  
**Location:** https://github.com/TheAtticusProject/cuad  

### Key Details
- Real-world commercial contracts from the CUAD dataset (510 contracts, 41 expert-annotated clause categories), raw text/PDF available.
- Teams must implement strict preprocessing rules to handle document length variance and ensure text cleaning captures the necessary legal terminology for high-accuracy classification.
- Per SME guidance, the team will select the 10 most impactful clause categories during the September milestone to scope the initial classification task, expanding to the full 41 categories only as a stretch goal.

---

## 🛠️ Suggested Approach
**ML Problem Type:** NLP & Classification  
**Recommended Libraries:** HuggingFace Transformers, PyTorch/TensorFlow, Scikit-learn, Pandas  
**Modeling Approach:** Fine-tune a pre-trained lightweight transformer encoder (e.g., `distilroberta-base` or DistilBERT) rather than training from scratch — this keeps fine-tuning feasible within free-tier Google Colab memory/batch-size constraints while still giving strong multi-label classification performance.  
**Evaluation Metrics:** Precision, Recall, F1-Score for classification; Spearman Correlation for risk-ranking alignment.

---

## 📚 Resources to Get Started

The following resources will help your team understand the problem space and potential technical approaches for this project:

**Background Reading:**
- [CUAD: An Expert-Annotated NLP Dataset for Legal Contract Review (paper)](https://arxiv.org/abs/2103.06268)
- [The Atticus Project — CUAD overview](https://www.atticusprojectai.org/cuad/)

**Technical Tutorials:**
- [HuggingFace — Text (sequence) classification tutorial](https://github.com/huggingface/transformers/blob/main/docs/source/en/tasks/sequence_classification.md)
- [HuggingFace — Multi-label classification walkthrough](https://huggingface.co/blog/Valerii-Knowledgator/multi-label-classification)

**Code Examples:**
- [CUAD official GitHub repo (baseline models, data loaders)](https://github.com/TheAtticusProject/cuad)
- [DistilRoBERTa base model card](https://huggingface.co/distilbert/distilroberta-base)

**Other:**
- [scipy.stats.spearmanr documentation (for risk-ranking evaluation)](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)

*Feel free to explore beyond these, and share anything interesting you find with me!*

---

## 🤝 How We'll Work Together

**Official check-ins:** During our biweekly 45-minute AI Studio Lab Section meeting block (2nd and 4th week of every month)

**Other ways to reach out to me with questions:**
* TODO (Adarsh): add your team's preferred contact channel(s) — e.g., a Discord channel, email (cc teammates + AI Studio Coach), or Zoom check-in requests.
* [Note: I will aim to respond within 48 hours. Please reach out to your AI Studio Coach with urgent questions.]

**Recommended free coding / collaboration tools**
* TODO (Adarsh): list any specific tools you'd like the team to use (e.g., Google Colab, GitHub, Slack/Discord). Google Colab is recommended given the free-tier compute constraints noted above.

---

## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Begin reviewing the dataset** using the link above
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

I'm excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session C).
