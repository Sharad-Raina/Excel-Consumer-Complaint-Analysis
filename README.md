# Consumer Complaints Analysis

## Overview
This project analyzes consumer complaints data to extract insights about complaint trends, company performance, and resolution times. The dataset includes consumer complaints along with relevant details such as the company involved, issue type, state, and resolution status.

## Dataset
- **Consumer_Complaints**: Contains raw consumer complaint data.
- **State_Code_Name**: Contains mapping of state codes to state names.
- **Task 1 - 5**: Each task focuses on different aspects of the data, including transformation, aggregation, and visualization.

## Tasks and Analysis
### Task 1: Data Preparation and Transformation
- Merge `State_Code_Name` with `Consumer_Complaints`.
- Extract state names and state codes from JSON format.
- Standardize column names for consistency.

#### Code Example:
```excel
=LEFT(A2, FIND(",", A2)-1)  # Extract state name from JSON text
=RIGHT(A2, LEN(A2)-FIND(",", A2)-1)  # Extract state code
```

### Task 2: Date-Based Analysis
- Calculate resolution time (in days) for complaints.
- Extract year and quarter from complaint dates.

#### Code Example:
```excel
=DATEDIF(B2, C2, "D")  # Calculate resolution time in days
=YEAR(B2)  # Extract year from complaint date
=ROUNDUP(MONTH(B2)/3, 0)  # Extract quarter from complaint date
```

### Task 3: Company-Wise Reporting
- Compute total complaints per company.
- Find the percentage of complaints where a timely response was given.
- Analyze disputed complaints.

#### Code Example:
```excel
=COUNTIF(A:A, D2)  # Count total complaints per company
=COUNTIFS(A:A, D2, B:B, "Yes")/COUNTIF(A:A, D2)  # Calculate timely response rate
```

### Task 4: Identifying Trends
- Find top five companies with the most complaints.
- Identify the most common complaint issues.
- Analyze complaint trends over time.

#### Code Example:
```excel
=LARGE(A:A, 1)  # Get top complaint counts
=INDEX(A:A, MATCH(LARGE(A:A, 1), A:A, 0))  # Get company with highest complaints
```

### Task 5: Dashboard KPIs
- Calculate key performance indicators (KPIs), including total complaints, timely responses, and dispute rates.
- Create visualizations to display trends.

#### Code Example:
```excel
=COUNT(A:A)  # Total complaints
=COUNTIF(B:B, "Yes")  # Number of timely responses
=COUNTIF(C:C, "Disputed")/COUNT(A:A)  # Dispute rate
```
<img width="1286" alt="Screenshot 2025-02-07 at 7 13 59 PM" src="https://github.com/user-attachments/assets/e4c62d24-13ed-47b8-b9b5-8af5625092f5" />



## Conclusion
This analysis provides valuable insights into consumer complaints, helping to identify trends and improve company responsiveness. The project leverages Excel functions for data wrangling, visualization, and statistical analysis.

