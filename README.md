# Healthcare Patient Analytics Dashboard

Tools: Power BI, SQL Server, Excel / Power Query  
Dataset: 55,500 healthcare patient records

Interactive dashboard for patient admissions, billing, medical conditions, length of stay, insurance, and test results.

## Dashboard preview
![Healthcare Patient Analytics Power BI Dashboard](images/dashboard.png)

## Business questions
- How many patients were admitted, and what is total vs average billing?
- How does length of stay relate to billing and medical condition?
- Which insurance providers and conditions drive volume?
- How do admission types (Elective, Urgent, Emergency) compare?
- What share of test results are Normal, Abnormal, or Inconclusive?
- How do metrics change by age group (Child, Young Adult, Adult, Senior)?

## KPIs
- Total patients: 55.5K
- Total billing: $1.42B
- Average billing: $25.54K
- Average length of stay: 15.5 days

## Visuals
- KPI cards
- Patient admissions over time
- Length of stay vs billing by medical condition
- Patients by admission type
- Patients by insurance provider
- Patients by medical condition
- Test results (Abnormal, Normal, Inconclusive)
- Age group slicer

## Data preparation
- Imported the dataset into SQL Server
- Set negative billing amounts to 0
- Calculated Length of Stay = Discharge Date minus Admission Date
- Created Age Group (Child, Young Adult, Adult, Senior)
- Loaded the cleaned table into Power BI

```sql
SELECT
    Name,
    Age,
    Gender,
    Blood_Type,
    Medical_Condition,
    Date_of_Admission,
    Discharge_Date,
    Insurance_Provider,
    Admission_Type,
    Test_Results,
    CASE WHEN Billing_Amount < 0 THEN 0 ELSE Billing_Amount END AS Billing_Amount,
    DATEDIFF(DAY, Date_of_Admission, Discharge_Date) AS Length_of_Stay
FROM healthcare.dbo.healthcare;


## Tools
SQL · SQL Server · Excel · Power Query · Power BI · Tableau · KPI Dashboards


