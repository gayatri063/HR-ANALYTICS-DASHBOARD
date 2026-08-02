# 📊 HR Analytics & Employee Attrition Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Data Analytics](https://img.shields.io/badge/Data_Analytics-HR_Insights-blue?style=for-the-badge&logo=googleanalytics&logoColor=white)](https://powerbi.microsoft.com/)
[![Dataset](https://img.shields.io/badge/Dataset-IBM_HR_Attrition-green?style=for-the-badge&logo=kaggle&logoColor=white)](d:\power-bi\hr%20data\WA_Fn-UseC_-HR-Employee-Attrition.csv)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)]()

An interactive, data-driven **Human Resources Analytics & Attrition Dashboard** built in **Power BI** utilizing IBM's HR Employee Attrition dataset (`WA_Fn-UseC_-HR-Employee-Attrition.csv`). This project provides HR leadership and business executives with strategic insights into employee retention, departmental attrition rates, salary distributions, demographic risk factors, and workforce tenure trends.

---

## 📌 Table of Contents
- [Executive Summary](#-executive-summary)
- [Key Business Metrics (KPIs)](#-key-business-metrics-kpis)
- [Dataset Architecture](#-dataset-architecture)
- [Power BI Dashboard Components](#-power-bi-dashboard-components)
- [Key Analytical Insights & Findings](#-key-analytical-insights--findings)
- [DAX Data Modeling & Measures](#-dax-data-modeling--measures)
- [Strategic HR Recommendations](#-strategic-hr-recommendations)
- [How to Run & Setup](#-how-to-run--setup)
- [Project Repository Structure](#-project-repository-structure)

---

## 📑 Executive Summary

Employee turnover poses significant financial and operational challenges to organizations due to recruitment costs, onboarding overheads, and lost productivity. The primary objective of this dashboard (`HR ANALYSIS DASHBOARD.pbix`) is to diagnose the underlying root causes of employee attrition and empower HR business partners with predictive intelligence to optimize retention strategies.

### Primary Objectives:
1. **Quantify Attrition Metrics**: Establish baseline KPIs for overall attrition rate, active workforce count, and total headcount.
2. **Identify Risk Demographics**: Analyze how factors such as age, gender, education field, and tenure correlate with employee exits.
3. **Department & Role Vulnerability**: Highlight high-turnover job roles (e.g., Sales Representatives, Lab Technicians) and departments requiring immediate intervention.
4. **Compensation Analysis**: Evaluate salary distribution across job roles to detect pay equity gaps or compensation-driven turnover.

---

## 📈 Key Business Metrics (KPIs)

| Metric | Value | Description |
| :--- | :--- | :--- |
| **Total Employees** | **1,470** | Total employee workforce headcount evaluated in the analysis |
| **Active Employees** | **1,233** | Retained workforce currently employed (83.88% retention rate) |
| **Attrition Count** | **237** | Total number of employees who departed the organization |
| **Attrition Rate** | **16.12%** | Proportion of total workforce lost to voluntary/involuntary exits |
| **Average Age** | **36.9 Years** | Mean age of the overall employee dataset |
| **Average Monthly Income**| **$6,502.93** | Average monthly base salary across all job levels |
| **Average Tenure at Company**| **7.0 Years** | Average length of employment service |
| **Average Distance From Home**| **9.2 Miles** | Mean commute distance for employees |

---

## 📁 Dataset Architecture

The underlying dataset **`WA_Fn-UseC_-HR-Employee-Attrition.csv`** consists of **1,470 rows** and **35 columns**, representing a comprehensive IBM Watson HR dataset.

### Key Data Attributes:

| Category | Field Name | Data Type | Description |
| :--- | :--- | :--- | :--- |
| **Demographics** | `Age`, `Gender`, `MaritalStatus`, `Education`, `EducationField` | Numeric / Text | Age, gender breakdown, marital status, and educational background |
| **Job Details** | `Department`, `JobRole`, `JobLevel`, `StandardHours`, `OverTime` | Text / Numeric | Organizational structure, hierarchy level, and overtime indicators |
| **Compensation** | `MonthlyIncome`, `MonthlyRate`, `DailyRate`, `HourlyRate`, `PercentSalaryHike`, `StockOptionLevel` | Numeric | Total compensation, hourly/monthly pay structure, equity, and salary hikes |
| **Tenure & History** | `YearsAtCompany`, `YearsInCurrentRole`, `YearsSinceLastPromotion`, `YearsWithCurrManager`, `TotalWorkingYears` | Numeric | Complete service timeline and career progression markers |
| **Employee Experience** | `EnvironmentSatisfaction`, `JobSatisfaction`, `WorkLifeBalance`, `JobInvolvement`, `RelationshipSatisfaction` | Numeric (1-4 Rating) | Survey sentiment scores for workplace satisfaction |
| **Target Variable** | `Attrition` | Text (`Yes` / `No`) | Indicates whether the employee departed the company |

---

## 🖥️ Power BI Dashboard Components

The Power BI file **`HR ANALYSIS DASHBOARD.pbix`** aggregates key metrics into an interactive single-page executive overview containing **10 core visual containers**:

```
+---------------------------------------------------------------------------------------------------+
|                                  HR ANALYSIS DASHBOARD HEADER                                     |
+-------------------+-------------------+-------------------+-------------------+-------------------+
|  TOTAL EMPLOYEES  |  ACTIVE EMPLOYEES |  ATTRITION COUNT  |  ATTRITION RATE   |    AVG INCOME     |
|       1,470       |       1,233       |        237        |      16.12%       |     $6,502.93     |
+-------------------+-------------------+-------------------+-------------------+-------------------+
| ATTRITION BY GENDER [Donut Chart]     | ATTRITION BY DEPARTMENT [Bar Chart]                       |
| - Male: 150 (63.3%)                   | - R&D: 133 (56.1%)                                        |
| - Female: 87 (36.7%)                  | - Sales: 92 (38.8%)                                       |
|                                       | - HR: 12 (5.1%)                                           |
+---------------------------------------+-----------------------------------------------------------+
| ATTRITION BY JOB ROLE [Clustered Column Chart]                                                    |
| - Lab Technician: 62 | Sales Exec: 57 | Research Scientist: 47 | Sales Rep: 33                     |
+---------------------------------------+-----------------------------------------------------------+
| ATTRITION BY EDUCATION FIELD [Pie]    | ATTRITION COUNT BY YEARS AT COMPANY [Line Chart]          |
| - Life Sciences, Medical, Marketing   | Peak attrition occurs between 1 to 3 years of service    |
+---------------------------------------+-----------------------------------------------------------+
| ATTRITION COUNT BY AGE GROUP [Column] | SALARY DISTRIBUTION BY JOB ROLE [Treemap]                 |
| - 18-25: 35.8% | 26-35: 19.1%        | - Managers & Research Directors command top income        |
+---------------------------------------+-----------------------------------------------------------+
| TOTAL EMPLOYEES MATRIX SUMMARY TABLE  | Multi-dimensional crosstab breakdown                      |
+---------------------------------------+-----------------------------------------------------------+
```

### Detailed Visual Inventory:

| # | Visual Type | Title in Dashboard | Analytical Focus |
| :-: | :--- | :--- | :--- |
| **1** | `Card Visual` | **KPI Summary Cards** | Total Headcount (1,470), Attrition Count (237), Attrition Rate (16.12%), Active Staff (1,233) |
| **2** | `Donut Chart` | **ATTRITION BY GENDER** | Male attrition (150 / 17.0%) vs. Female attrition (87 / 14.8%) |
| **3** | `Bar Chart` | **ATTRITION BY DEPARTMENT** | Departmental turnover comparison (Sales: 20.6%, R&D: 13.8%, HR: 19.1%) |
| **4** | `Clustered Column` | **ATTRITION BY JOB ROLE** | Turnover count by role (Lab Techs: 62, Sales Execs: 57, Research Scientists: 47) |
| **5** | `Pie Chart` | **ATTRITION BY EDUCATION FIELD** | Distribution across Life Sciences (89), Medical (63), Marketing (35), Tech Degrees (32) |
| **6** | `Line Chart` | **ATTRITION COUNT BY YEARS AT COMPANY** | Identifies critical tenure drop-off zones (high attrition within years 1–3) |
| **7** | `Column Chart` | **ATTRITION COUNT BY AGE GROUP** | Age cohort analysis (18–25 age group has the highest rate at 35.77%) |
| **8** | `Treemap` | **SALARY DISTRIBUTION BY JOB ROLE** | Visual hierarchy of average monthly income across positions |
| **9** | `Pivot Table` | **TOTAL EMPLOYEES MATRIX** | Cross-tabular breakdown of employee metrics |

---

## 💡 Key Analytical Insights & Findings

### 1. 🚨 High-Risk Job Roles
- **Sales Representatives** experience the highest attrition rate across the company at **39.76%** (33 out of 83 employees left).
- **Laboratory Technicians** account for the highest total turnover count (**62 departures**, **23.94% attrition rate**).
- **Human Resources** staff follow closely with **23.08%** attrition rate.
- Conversely, executive positions show extreme stability: **Research Directors** (**2.50%**) and **Managers** (**4.90%**).

### 2. ⏳ Tenure & Early Career Departure Trend
- Attrition peaks heavily during the first **1 to 3 years** of employment service.
- Employees who stay beyond **5 years** exhibit significantly higher long-term retention.

### 3. 🎓 Age Group & Demographics Impact
- **Younger Workforce (18–25 Years)**: Attrition rate spikes at **35.77%** (44 out of 123 employees left), indicating onboarding or career-path mismatch.
- **Mid-Career (36–45 Years)**: Lowest attrition rate at **9.19%**, indicating career stability.
- **Gender Dynamics**: Male employees account for **63.3% of total turnover** (150 departures; 17.01% rate) compared to Females (87 departures; 14.80% rate).

### 4. 💵 Compensation Disparity
- **Executive Compensation**: Managers ($17,181 avg) and Research Directors ($16,034 avg) command the top salary brackets.
- **Entry-Level Compensation**: Sales Representatives ($2,626 avg) and Laboratory Technicians ($3,237 avg) operate at lower salary bands, matching the exact roles exhibiting the highest turnover.

---

## 🧮 DAX Data Modeling & Measures

The following **Data Analysis Expressions (DAX)** formulas were created and used within the Power BI data model to calculate core measures dynamically:

```dax
// 1. Total Employees Count
Total Employees = COUNT('WA_Fn-UseC_-HR-Employee-Attrition'[EmployeeNumber])

// 2. Attrition Count
Attrition Count = CALCULATE(
    COUNT('WA_Fn-UseC_-HR-Employee-Attrition'[EmployeeNumber]),
    'WA_Fn-UseC_-HR-Employee-Attrition'[Attrition] = "Yes"
)

// 3. Active Employees Count
Active Employees = CALCULATE(
    COUNT('WA_Fn-UseC_-HR-Employee-Attrition'[EmployeeNumber]),
    'WA_Fn-UseC_-HR-Employee-Attrition'[Attrition] = "No"
)

// 4. Attrition Rate (%)
Attrition Rate = DIVIDE([Attrition Count], [Total Employees], 0)

// 5. Average Age
Average Age = AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[Age])

// 6. Average Monthly Income
Average Monthly Income = AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[MonthlyIncome])

// 7. Average Years at Company
Average Tenure = AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[YearsAtCompany])
```

---

## 🎯 Strategic HR Recommendations

Based on empirical data findings from this dashboard, HR management should implement the following interventions:

1. **Restructure Sales Representative Incentives**: Given the alarming **39.76% attrition rate** among Sales Reps, review base pay structures, commission targets, and working hours (overtime management).
2. **Lab Technician Career Pathways**: Address the **23.94% attrition** in Laboratory Technicians by providing structured career advancement roadmaps and skill development programs.
3. **Targeted Early-Tenure Engagement**: Implement 30-60-90 day onboarding check-ins and mentorship programs to combat the peak turnover observed in years 1–3.
4. **Youth Retention & Mentorship (18–25 Cohort)**: Provide early-career employees (35.77% attrition) with clear growth opportunities, competitive entry-level salaries, and flexible work-life balance initiatives.

---

## 🛠️ How to Run & Setup

### Prerequisites
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Free Download)
- Python 3.8+ (Optional, for running automated custom scripts)

### Installation Steps
1. **Clone or Download the Repository**:
   ```bash
   git clone https://github.com/your-username/hr-analytics-powerbi.git
   cd hr-analytics-powerbi
   ```
2. **Open the Power BI Dashboard**:
   - Double-click **`HR ANALYSIS DASHBOARD.pbix`** to launch the report in Power BI Desktop.
3. **Update Data Source Path** (If prompted):
   - In Power BI Desktop, click **Transform Data** > **Data Source Settings**.
   - Browse and select the local path to **`WA_Fn-UseC_-HR-Employee-Attrition.csv`**.
   - Click **Apply Changes** to refresh visuals with current data.

---

## 📂 Project Repository Structure

```
d:\power-bi\hr data/
│
├── 📊 HR ANALYSIS DASHBOARD.pbix         # Primary Power BI Report file containing layout & visuals
├── 📄 WA_Fn-UseC_-HR-Employee-Attrition.csv # IBM HR Watson dataset (1,470 records, 35 fields)
└── 📝 README.md                            # Complete project documentation & analytical overview
```

---

## 👤 Author & Acknowledgments

- **Developer**: Gayatri
- **Domain**: Human Resources & Workforce Analytics
- **Dataset Source**: IBM HR Employee Attrition & Performance Dataset
- **Tools Used**: Microsoft Power BI Desktop, DAX, Python, Data Modeling

---
*If you find this project useful, feel free to ⭐ star the repository on GitHub!*
