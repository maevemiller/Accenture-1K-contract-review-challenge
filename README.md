# AI Studio Challenge Project Title

> 💡 **Note for the team:** This is just a template. Update the above title with your AI Studio Challenge Project name. Remove all guidance notes and example text in this template and populate this README with your own content. You can work on this README throughout AI Studio, and get feedback from your AI Studio Coach and Challenge Advisor before finalizing it.  

---

### 👥 **Team Members**

**Example:**

| Name             | GitHub Handle | Contribution                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
| Taylor Nguyen    | @taylornguyen | Data exploration, visualization, overall project coordination            |
| Jordan Ramirez   | @jramirez     | Data collection, exploratory data analysis (EDA), dataset documentation  |
| Amina Hassan     | @aminahassan  | Data preprocessing, feature engineering, data validation                 |
| Priya Mehta      | @pmehta       | Model selection, hyperparameter tuning, model training and optimization  |
| Chris Park       | @chrispark    | Model evaluation, performance analysis, results interpretation           |

---

## 🎯 **Project Highlights**

**Example:**

- Developed a machine learning model using `[model type/technique]` to address `[challenge project task]`.
- Achieved `[key metric or result]`, demonstrating `[value or impact]` for `[host company]`.
- Generated actionable insights to inform business decisions at `[host company or stakeholders]`.
- Implemented `[specific methodology]` to address industry constraints or expectations.

---

## 👩🏽‍💻 **Setup and Installation**

**Provide step-by-step instructions so someone else can run your code and reproduce your results. Depending on your setup, include:**

* How to clone the repository
* How to install dependencies
* How to set up the environment
* How to access the dataset(s)
* How to run the notebook or scripts

---

## 🏗️ **Project Overview**

**Describe:**

- How this project is connected to the Break Through Tech AI Program
- Your AI Studio host company and the project objective and scope
- The real-world significance of the problem and the potential impact of your work

Clause detection covers **10** of CUAD's 41 clause categories:

1. Governing Law
2. Anti-Assignment
3. Cap On Liability
4. License Grant
5. Audit Rights
6. Termination For Convenience
7. Exclusivity
8. Change Of Control
9. Non-Compete
10. Uncapped Liability

Full 41-category coverage is a stretch goal, not core scope. This list is pending confirmation at the first advisor meeting (week of Aug 24).

---

## 📊 **Data Exploration**

**You might consider describing the following (as applicable):**

* The dataset(s) used: origin, format, size, type of data
* Data exploration and preprocessing approaches
* Insights from your Exploratory Data Analysis (EDA)
* Challenges and assumptions when working with the dataset(s)

**Potential visualizations to include:**

* Plots, charts, heatmaps, feature visualizations, sample dataset images

### Dataset: CUAD

[CUAD](https://github.com/TheAtticusProject/cuad) (Contract Understanding Atticus Dataset) — 510 contracts, 41 expert-annotated clause categories, distributed as SQuAD-style QA JSON (`CUADv1.json`), not a flat CSV. Each category has a question per contract; a clause is "present" when the QA item has a non-empty `answers` list and `is_impossible: false`.

**Per-category support, computed directly from `CUADv1.json`** (number of the 510 contracts containing each clause, for the 10 selected categories):

| Category | Contracts | % of 510 |
|---|---|---|
| Governing Law | 437 | 85.7% |
| Anti-Assignment | 374 | 73.3% |
| Cap On Liability | 275 | 53.9% |
| License Grant | 255 | 50.0% |
| Audit Rights | 214 | 42.0% |
| Termination For Convenience | 183 | 35.9% |
| Exclusivity | 180 | 35.3% |
| Change Of Control | 121 | 23.7% |
| Non-Compete | 119 | 23.3% |
| Uncapped Liability | 111 | 21.8% |

The 5 most frequent categories overall (Document Name, Parties, Agreement Date, Expiration Date, Effective Date — all 76–100% of contracts) were deliberately excluded: they're contract metadata, not risk clauses, so out of scope for risk scoring.

**Preprocessing note:** to avoid the raw-PDF/token-alignment overhead CUAD is known for, this project treats detection as **per-category presence/absence classification** using `CUADv1.json`'s existing `answers`/`is_impossible` fields, rather than extracting exact token-level clause spans from raw PDF text. Token-level span extraction is a stretch goal, not core scope.

---

## 🧠 **Model Development**

**You might consider describing the following (as applicable):**

* Model(s) used (e.g., CNN with transfer learning, regression models)
* Feature selection and Hyperparameter tuning strategies
* Training setup (e.g., % of data for training/validation, evaluation metric, baseline performance)

**DistilRoBERTa**, fine-tuned for multi-label classification across the 10 selected categories. A TF-IDF/keyword baseline is built first (see `notebooks/02_baseline_tfidf.ipynb`) to give the fine-tuned model something concrete to beat.


---

## 📈 **Results & Key Findings**

**You might consider describing the following (as applicable):**

* Performance metrics (e.g., Accuracy, F1 score, RMSE)
* How your model performed
* Insights from evaluating model fairness

**Potential visualizations to include:**

* Confusion matrix, precision-recall curve, feature importance plot, prediction distribution, outputs from fairness or explainability tools

---

## 🚀 **Next Steps**

**You might consider addressing the following (as applicable):**

* What are some of the limitations of your model?
* What would you do differently with more time/resources?
* What additional datasets or techniques would you explore?

---

## 📝 **License**

Specify how your project can be used by others. Choose an appropriate license and link it here (e.g., MIT, Apache 2.0). Make sure your Challenge Advisor approves of the selected license type. 

**Example:**
This project is licensed under the MIT License.

---

## 📄 **References** (Optional but encouraged)

Cite relevant papers, articles, or resources that supported your project.

---

## 🙏 **Acknowledgements** (Optional but encouraged)

Thank your Challenge Advisor, host company representatives, TA, and others who supported your project.
