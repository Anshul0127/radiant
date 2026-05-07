excel formulas
1. avergage - 
AVERAGEIFS(
average_range,
criteria_range1, criteria1,
criteria_range2, criteria2
)


=AVERAGEIFS(Sales_Data!F:F,Sales_Data!B:B,B2,Sales_Data!C:C,B3)


2) Adaptability Formula Structure
IF(
condition,
value if true,
value if false
)

=IF(B4>700000,"High Sales","Low Sales")


3) Integration Formula Structure
SUMIFS(
sum_range,
criteria_range1,criteria1,
criteria_range2,criteria2
)

=SUMIFS(Sales_Data!F:F,Sales_Data!B:B,B2,Sales_Data!C:C,B3)


4) what if analysis - =(B2*$B$6)+(C2*$C$6)+(D2*$D$6) - for ev 

5 - best decision in what if analysis - =INDEX(A2:A4,MATCH(MAX(E2:E4),E2:E4,0))

6 - solver -

Example:
Total Reach
=(B2*B5)+(B3*B6)
Meaning:
(Reach per social ad × number of social ads)
+
(Reach per TV ad × number of TV ads)

✅ STEP 4 — Create Constraints
Total Cost
=(C2*B5)+(C3*B6)

Total Time
=(D2*B5)+(D3*B6)

✅ STEP 5 — Add Limits
Example:
Constraint
Limit
Budget
5000
Time
40

✅ STEP 6 — Open Solver
Go:
 👉 Data → Solver

✅ STEP 7 — Solver Setup

🔹 Set Objective
Select:
 👉 Total Reach cell
Choose:
 👉 Max

🔹 By Changing Variable Cells
Select:
 👉 variable cells
Example:
B5:B6

🔹 Add Constraints
Budget
Total Cost <= Budget Limit

Time
Total Time <= Time Limit

Non-negative
Variables >= 0

✅ STEP 8 — Solver Method
Choose:
 👉 Simplex LP
MOST IMPORTANT.

✅ STEP 9 — Solve
Click:
 👉 Solve


standalone dss- ✅ STEP 1 — Create New DSS Sheet
Example:
A8_Standalone_DSS

✅ STEP 2 — Add Inputs
Usually:
dropdowns
filters
Example:
Select Product
Select Region
Select Department

🔥 Why?
These make system:
 ✅ interactive.

✅ STEP 3 — Create Dropdowns
Data → Data Validation → List
Use dataset columns as source.

✅ STEP 4 — Add Processing Formulas
This is the MAIN DSS logic.

🔥 Common formulas
SUMIFS
Used for totals.
=SUMIFS(...)
Example:
=SUMIFS(sales_data!F:F,sales_data!C:C,B2)

AVERAGEIFS
Used for averages.
=AVERAGEIFS(...)
Example:
=AVERAGEIFS(main_data!S:S,main_data!E:E,B2)

COUNTIFS
Used for counts.
=COUNTIFS(...)
Example:
=COUNTIFS(main_data!E:E,B2,main_data!B:B,"Yes")

✅ STEP 5 — Add Outputs
Examples:
Total Sales
Units Sold
Employees Leaving
Average Salary
These update dynamically.

✅ STEP 6 — Add Decision Logic
Use:
 👉 IF formulas.

🔥 Example
=IF(B6>20,"High Risk","Normal")
Meaning:
if employees leaving > 20
 → High Risk

✅ STEP 7 — Add Recommendation
This makes it a TRUE DSS.

🔥 Example
=IF(B7="High Risk","Improve employee retention","Current policies effective")

💡 Meaning
System not only analyzes:
 👉 it recommends action.

🎯 FINAL STRUCTURE
Input
Processing
Output
Recommendation
Dropdowns
SUMIFS/COUNTIFS
Results
IF logic


