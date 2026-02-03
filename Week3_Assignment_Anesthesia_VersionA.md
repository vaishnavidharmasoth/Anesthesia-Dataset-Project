# Week 3 Assignment: Anesthesia Dataset Analysis

## I 320D: Data Science for Biomedical Informatics | Spring 2026

### 📋 Assignment Version A

---

## 🎯 This Week's Mantra

> **"Every Column Tells a Story"**

In this assignment, you'll apply the 10-Point Data Inspection to a real-world healthcare dataset focused on anesthesia outcomes. By the end, you'll understand not just *what* the data contains, but *why* each variable matters for clinical decision-making and patient safety.

---

## Learning Objectives

By completing this assignment, you will be able to:

1. ✅ Apply the systematic 10-Point Inspection to a healthcare dataset
2. ✅ Identify and classify feature types (continuous, discrete, categorical, ordinal)
3. ✅ Detect and document data quality issues (missing values, unexpected values)
4. ✅ Research and document clinical meaning for healthcare variables
5. ✅ Create meaningful data groupings based on clinical standards
6. ✅ Formulate answerable research questions about anesthesia outcomes

---

## About the Dataset

**Dataset:** Anesthesia Patient Outcomes  
**File:** `Anesthesia_Dataset.csv`  
**Target Variable:** `Outcome` (surgical outcome: 0 = unsuccessful, 1 = successful)

### Clinical Context

Anesthesia management is a critical component of surgical care, directly impacting patient safety and surgical outcomes. This dataset contains patient information that anesthesiologists and surgical teams use to assess risk factors, plan anesthesia protocols, and predict potential complications. Understanding these variables is crucial for:

- Pre-operative risk assessment and patient optimization
- Anesthesia type selection based on patient characteristics
- Post-operative complication prediction and prevention
- Quality improvement in surgical care
- Resource allocation and surgical planning

---

## Getting Started

First, load the dataset and import your libraries:

```python
# Import libraries


# Load the dataset


# Display first few rows to confirm it loaded

```

---

## Part 1: The 10-Point Data Inspection (40 points)

Complete each inspection step and document your findings.

### Step 1: Shape (4 points)

**Your Code:**
```python

```

**Your Findings:**
- How many rows (observations)? _______________
- How many columns (features)? _______________
- What does each row represent in clinical terms? _______________

---

### Step 2: Column Names (4 points)

**Your Code:**
```python

```

**Your Findings:**
- List all column names:

- Which columns might need further research to understand?

---

### Step 3: Data Types (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns are numeric?

- Which columns are categorical (object/string)?

- Are there any data types that seem incorrect? (Hint: Look at SurgeryDuration)

---

### Step 4: First Look (4 points)

**Your Code:**
```python

```

**Your Findings:**
- What do the actual values look like?

- Do you notice anything unusual or unexpected?

- Are there any values that might need cleaning before analysis?

---

### Step 5: Last Look (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Does the data end cleanly?

- Are the last rows consistent with the first rows?

---

### Step 6: Memory Usage (4 points)

**Your Code:**
```python

```

**Your Findings:**
- How much memory does the dataset use? _______________ KB/MB
- Is this a "small" or "large" dataset by data science standards?

---

### Step 7: Missing Values (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns have missing values (according to `.isnull()`)?

- What percentage of each column is missing?

- Are there any columns where missing data might be clinically significant?

---

### Step 8: Duplicates (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Are there any duplicate rows? _______________
- Are all patient IDs unique? _______________
- Why is it important to check for duplicates in medical data?

---

### Step 9: Basic Statistics (4 points)

**Your Code:**
```python

```

**Your Findings:**
- What is the age range in the dataset? _______________ to _______________
- What is the range of BMI values? _______________ to _______________
- What is the range of PainLevel values? _______________ to _______________
- Do any min/max values seem impossible or clinically unlikely?

---

### Step 10: Unique Counts (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns have very few unique values (likely categorical)?

- Which columns have many unique values (likely continuous or IDs)?

- Does the number of unique PatientIDs match the number of rows? _______________

---

## Part 2: Data Dictionary (20 points)

Complete the following data dictionary. For each column, you must:
1. **Research** the clinical meaning
2. **Identify** the feature type (Continuous, Discrete, Categorical-Nominal, Categorical-Ordinal, Binary, Identifier)
3. **Document** the valid values/range you observe
4. **Note** any issues or questions

| Column | Description | Feature Type | Valid Values/Range | Notes/Issues |
|--------|-------------|--------------|-------------------|--------------|
| `PatientID` | | | | |
| `Age` | | | | |
| `Gender` | | | | |
| `BMI` | | | | |
| `SurgeryType` | | | | |
| `SurgeryDuration` | | | | |
| `AnesthesiaType` | | | | |
| `PreoperativeNotes` | | | | |
| `PostoperativeNotes` | | | | |
| `PainLevel` | | | | |
| `Complications` | | | | |
| `Outcome` | | | | |

### Clinical Research Questions for Version A

Answer these questions based on your research (you may need to use external sources):

**1. What are the main types of anesthesia (General, Local, Regional, etc.)? What are the key differences in terms of patient risk and recovery?**

Your answer:

---

**2. What is the clinical significance of BMI in anesthesia risk assessment? At what BMI levels do anesthesiologists typically consider a patient "high-risk"?**

Your answer:

---

**3. What are the most common complications that can occur during or after anesthesia? Which ones in this dataset are considered serious?**

Your answer:

---

**4. How is post-operative pain typically measured in clinical settings? What does a pain scale of 1-10 represent?**

Your answer:

---

## Part 3: Data Validation (15 points)

### 3.1 Age Validation (5 points)

Write code to check:
- How many ages are below 18?
- How many ages are above 90?
- What is the actual age range?
- What is the distribution of ages by decade?

**Your Code:**
```python

```

**Your Findings:**

- Are there any impossible age values?

- What age groups are most represented in surgical patients?

- Does this distribution make clinical sense for elective surgeries?

---

### 3.2 Surgery Duration Validation (5 points)

Write code to examine SurgeryDuration values closely. Notice that the values include " min" as text.

**Your Code:**
```python

```

**Your Findings:**

- What is the format of the SurgeryDuration column?

- How would you convert this to a numeric value for analysis?

- What is the range of surgery durations once converted?

- Are there any surgery durations that seem unusually short or long?

---

### 3.3 Complications Validation (5 points)

Write code to see all unique values and their counts for the Complications column.

**Your Code:**
```python

```

**Your Findings:**

- What are all the possible complication values?

- How many patients had "None" for complications?

- What percentage of patients experienced some form of complication?

- Are there any complications that might be considered more serious than others?

---

## Part 4: Create Clinical Age Groups (10 points)

Create a new column called `age_group` that categorizes patients into clinically-meaningful groups.

### Version A: Anesthesia Risk Categories

Use these categories based on anesthesia risk considerations:

| Age Group | Range | Clinical Rationale |
|-----------|-------|-------------------|
| Young Adult | 18-39 | Generally lowest anesthesia risk, rapid recovery |
| Middle Adult | 40-54 | Moderate risk, potential onset of comorbidities |
| Mature Adult | 55-64 | Increased perioperative risk factors |
| Senior | 65-74 | Significant anesthesia considerations |
| Elderly | 75+ | Highest risk, requires careful monitoring |

### Your Code:

```python
# Create the age_group column
# You can use a custom function with .apply() OR pd.cut()
# Remember: if using pd.cut(), use include_lowest=True!


```

### Verify your groupings worked:

```python
# Show counts per age group

```

### Calculate outcome rate by age group:

```python
# Calculate the percentage of successful outcomes in each age group

```

### Analysis Questions:

**1. How many patients are in each age group?**

Your answer:

---

**2. What is the successful outcome rate (percentage) for each age group?**

Your answer:

---

**3. At what age does surgical outcome appear to change most? Does this match what you learned in your clinical research about anesthesia risk?**

Your answer:

---

## Part 5: Research Questions (15 points)

### 5.1 Write Three Answerable Questions (9 points)

Write three questions that THIS dataset can answer. Remember: the data can show relationships and patterns, but cannot prove causation.

**Your questions must explore these specific areas:**

1. **A question about anesthesia type and complications:**


---

2. **A question comparing surgery types and outcomes:**


---

3. **A question about the combination of BMI AND surgery duration:**


---

### 5.2 Identify One Question the Data CANNOT Answer (3 points)

Write one question about **medication dosage or specific anesthesia protocols** that this dataset cannot answer, and explain why.

**Question:**


**Why it cannot be answered with this data:**


---

### 5.3 Grouping Analysis (3 points)

Answer this question using a groupby analysis:

**"What is the average pain level for each surgery type?"**

**Your Code:**
```python

```

**Your Interpretation:**

Which surgery type has the highest average pain level? Which has the lowest? What might explain these differences?


---

## Part 6: Target Variable Analysis (Bonus - 5 points)

The `Outcome` column is our **target variable** - representing surgical success. Analyze its distribution.

**Your Code:**
```python
# Show the count and percentage of successful vs unsuccessful outcomes

```

### Bonus Questions:

**1. What percentage of surgeries in this dataset had successful outcomes (Outcome = 1)?**

Your answer:

---

**2. Is this dataset balanced or imbalanced? (A balanced dataset has roughly equal classes)**

Your answer:

---

**3. Compare outcome rates between General and Local anesthesia. Is there a noticeable difference?**

Your answer:

---

**4. What additional information would you want to collect to better predict surgical outcomes?**

Your answer:

---

## Submission Checklist

Before submitting, verify you have completed:

- [ ] **Part 1:** All 10 inspection steps with code AND written findings
- [ ] **Part 2:** Complete data dictionary with all 12 columns filled in
- [ ] **Part 2:** Answered all 4 clinical research questions
- [ ] **Part 3:** All 3 validation checks with code and answers
- [ ] **Part 4:** Created `age_group` column using the **Anesthesia Risk Categories**
- [ ] **Part 4:** Calculated outcome rate by age group with interpretation
- [ ] **Part 5:** Three research questions (anesthesia/complications, surgery/outcomes, BMI+duration)
- [ ] **Part 5:** One unanswerable question about medication/protocols
- [ ] **Part 5:** Pain level by surgery type groupby analysis
- [ ] **Bonus (Optional):** Target variable analysis

---

## Grading Rubric

| Component | Points | Requirements for Full Credit |
|-----------|--------|------------------------------|
| Part 1: 10-Point Inspection | 40 | All 10 steps complete with working code AND thoughtful written analysis |
| Part 2: Data Dictionary | 20 | All 12 columns documented with correct feature types and clinical research |
| Part 3: Data Validation | 15 | All validation checks complete with working code and insightful answers |
| Part 4: Age Groups | 10 | Working code that creates correct groups AND meaningful interpretation |
| Part 5: Research Questions | 15 | Three good questions in specified areas, one clear limitation, groupby analysis complete |
| **Bonus:** Target Analysis | +5 | Thoughtful analysis of outcome distribution with clinical connections |
| **Total** | 100 (+5 bonus) | |

---

## Hints (Read Before You Get Stuck!)

### ⚠️ Common Pitfalls:

1. **SurgeryDuration contains text** - The values look like "217 min" which is a string, not a number. You'll need to extract the numeric portion before doing any calculations with this column.

2. **Multiple values in some columns** - PreoperativeNotes and Complications may contain multiple conditions separated by commas. Think about how this affects analysis.

3. **Outcome encoding** - Make sure you understand what 0 and 1 represent before interpreting your results.

4. **Age distribution** - This dataset contains adult surgical patients. The age groupings reflect perioperative risk categories.

### 💡 Pro Tips:

- Use `value_counts()` liberally to understand categorical columns
- Use `value_counts(dropna=False)` to see if there are any null values
- For the SurgeryDuration column, consider using string methods like `.str.replace()` to clean the data
- When something seems weird, investigate it—don't assume it's an error
- Always state what the data CAN tell you vs. what would require additional information

---

## Useful Resources

- **ASA Physical Status Classification:** https://www.asahq.org/standards-and-guidelines/asa-physical-status-classification-system
- **Anesthesia Types Overview:** https://www.asahq.org/madeforthismoment/preparing-for-surgery/types-of-anesthesia/
- **BMI and Surgical Risk:** https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4890841/
- **Pain Assessment Scales:** https://www.ncbi.nlm.nih.gov/books/NBK556098/
- **Pandas Documentation:** https://pandas.pydata.org/docs/

---

*Remember: "Every Column Tells a Story" - your job is to figure out what that story is!*

---

**Due Date:** [See Canvas]

**Submission:** Upload your completed Jupyter notebook (.ipynb) to Canvas
