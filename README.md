![Banner_Image](Visuals/Python_HR_Demo.png)

Python Fundamentals Demo: HR Engagement & Turnover Risk
Author: Antonique (Anna) Becker 

Description:
This script demonstrates foundational Python skills using a simple,
HR-relevant example. It focuses on core concepts such as dictionaries,
loops, conditional logic, and basic aggregation.

The example uses a small, sample employee dataset to identify:
- Employees with low engagement
- Employees who may be at higher turnover risk
- A basic department-level breakdown

This code is intentionally simple, self-contained, and easy to follow
to showcase Python fundamentals in an HR analytics context.

# Sample employee data stored in a dictionary
# Each employee ID maps to a set of HR-related metrics

employees = {
    "E001": {"department": "IT", "engagement": 4.5, "overtime": 0.1, "manager_satisfaction": 4.7},
    "E002": {"department": "Sales", "engagement": 3.8, "overtime": 0.6, "manager_satisfaction": 3.5},
    "E003": {"department": "Operations", "engagement": 3.1, "overtime": 1.2, "manager_satisfaction": 2.9},
    "E004": {"department": "HR", "engagement": 4.2, "overtime": 0.2, "manager_satisfaction": 4.3},
    "E005": {"department": "Finance", "engagement": 3.4, "overtime": 0.8, "manager_satisfaction": 3.1},
}


# Initialize variables to store results


high_risk_employees = []     # Employees flagged as higher turnover risk
low_engagement_count = 0     # Count of employees with low engagement


# Loop through each employee and evaluate conditions


for emp_id, data in employees.items():
    engagement = data["engagement"]
    overtime = data["overtime"]
    manager_sat = data["manager_satisfaction"]

    # Check for low engagement
    if engagement < 3.5:
        low_engagement_count += 1

    # Simple turnover risk rule:
    # High overtime combined with low manager satisfaction
    if overtime > 0.5 and manager_sat < 3.2:
        high_risk_employees.append(emp_id)

# Output summary results


print("HR Engagement Summary")
print("---------------------")
print(f"Total employees reviewed: {len(employees)}")
print(f"Employees with low engagement: {low_engagement_count}")

print("\nEmployees flagged as higher turnover risk:")
for emp in high_risk_employees:
    print(f"- {emp}")


# Department-level aggregation


department_counts = {}

for data in employees.values():
    dept = data["department"]
    department_counts[dept] = department_counts.get(dept, 0) + 1

print("\nEmployees by department:")
for dept, count in department_counts.items():
    print(f"{dept}: {count}")


# Results Summary


Results Summary:

This script reviewed a small sample of five employees to show how basic
Python logic can be applied to engagement and turnover risk in an HR
scenario.

Two employees were identified as having lower engagement. Using a simple
rule based on overtime levels and manager satisfaction, two employees
(E003 and E005) were flagged as potentially higher turnover risk. Both
employees showed higher overtime and lower satisfaction with their
managers, which are common indicators associated with retention issues.

The department summary shows an even distribution across IT, Sales,
Operations, HR, and Finance. While the dataset is small and used only
for demonstration, the same logic could scale to larger, real-world
HR datasets.

This example highlights how foundational Python skills—such as working
with dictionaries, loops, and conditional statements—can be used to
surface meaningful workforce insights in a clear and approachable way.

