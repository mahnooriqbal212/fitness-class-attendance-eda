# Fitness Class - EDA

## Overview
This project provides an exploratory data analysis (EDA) on a dataset of 1,500 fitness class bookings to identify the key behavioral and operational drivers of class attendance. Through systematic data cleaning, regex extraction, feature engineering, and statistical analysis, the workflow examines how member tenure, booking lead time, weight, and class type impact show-up rates. The final conclusions deliver actionable insights to help fitness studio managers optimize scheduling, allocate capacity efficiently, and improve overall attendance.

---

## Key Visual Findings

1. **Feature Distributions and Skewness (Histograms):**
   * **Membership Tenure (`months_as_member`):** Strongly right-skewed, showing that the majority of bookings come from newer members (concentrated around 0–15 months), with a long tail of veteran members exceeding 40+ months.
   * **Member Weight (`weight`):** Displays a roughly bell-shaped, normal distribution centered around 80–83 kg, with standard variance and a small number of outliers on the higher-weight tail.

2. **Member Tenure Drives Attendance (Heatmap):**
   * Membership length (`months_as_member`) is the single strongest positive predictor of attendance ($r = 0.49$). Longer-standing members consistently exhibit higher show-up probabilities, while member weight shows a slight inverse correlation ($r = -0.28$).

3. **HIIT Dominates Total Demand (Pie Chart):**
   * HIIT accounts for nearly half of all reservations (44.5%), followed by Cycling (25.1%) and Strength (15.5%), demonstrating where studio floor space and instructor resources are most required.

4. **Lead Time Independence (Heatmap / Groupby Analysis):**
   * Booking lead time (`days_before`) displays virtually zero linear correlation ($r = 0.02$) with attendance. Whether a client books two weeks in advance or on short notice does not meaningfully influence their likelihood of showing up.

5. **Attendance Rate vs. Volume Across Disciplines (Grouped Summary / Boxplot):**
   * While HIIT generates the largest raw volume, Aqua achieves the highest attendance efficiency rate (32.9%), whereas Strength ranks lowest (26.6%). An unlabelled category (`"-"`) was identified with a notably depressed attendance rate (15.4%), highlighting a data quality issue flagged for cleaning.

---

## Repository Structure

```text
├── fitness_class_2212.csv      # Raw fitness class booking dataset
├── fitness_class_eda.ipynb     # Jupyter / Colab analysis notebook
└── README.md                   # Project overview, findings, and setup instructions
```

## Setup & How to Run

### Option 1: Run in Google Colab (Fastest)

1. Open [Google Colab](https://colab.research.google.com/).
2. Click **File** $\rightarrow$ **Open notebook**, select the **GitHub** tab, and enter your repository URL.
3. Open `fitness_class_eda.ipynb`.
4. Upload `fitness_class_2212.csv` to the session storage:
   * Click the **Folder icon** (Files) in the left sidebar.
   * Click the **Upload** button and select `fitness_class_2212.csv`.
5. Run the notebook from top to bottom by clicking **Runtime** $\rightarrow$ **Run all** (or press `Ctrl + F9` / `Cmd + F9`).

---

### Option 2: Run Locally (Jupyter Notebook / VS Code)

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/fitness-class-attendance-eda.git
   cd fitness-class-attendance-eda
