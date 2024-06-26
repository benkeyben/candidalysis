## 2022-2023 Candidates Performance: Aggregates & Subjects Analysis in Schools in a Particular District in Ghana
<img src="img/candidalysis-banner.png" alt="candidalysis banner" style="width:100%;"/>

## Project Overview
The district education department within the Ghana Education Service lacks a comprehensive system for tracking key performance indicators (KPIs) such as enrollment, exam attendance, student aggregates, and subject-grade trends. This absence hampers their ability to effectively compare school and student performance and identify schools with high aggregate scores. There's a pressing need to streamline data collection, analysis, and visualization to facilitate informed decision-making and improve overall educational outcomes.

KEY PERFORMANCE INDICATORS (KPIs) include
  - Enrolment in Junior High School 3
  - Number of candidates registered
  - Number of candidates present during the examination
  - Number of candidates absent during the examination
  - Subject grades
  - Number of candidates obtaining aggregates as indicated below:
    - Aggregates 6
    - Aggregates 7 - 15
    - Aggregates 16 - 24
    - Aggregates 25 - 30
    - Aggregates 31 - 36
    - Aggregates 36 - 42
## Objectives (Data Analyst)
- Utilize Power BI Desktop to establish connections and transform raw HTML data files into a structured format conducive to analysis.
- Develop a comprehensive relational data model within Power BI Desktop, ensuring clear and effective relationships between different data entities.
- Employ Data Analysis Expressions (DAX) in Power BI Desktop to create calculated columns and measures, enabling advanced calculations and insights generation.
- Design and implement an interactive dashboard using Power BI Desktop, leveraging its visualization capabilities to present key metrics and trends in an intuitive and actionable manner.

## Tech Stack and Tools Used
- Data Extraction and Transformation: Excel Power Query Editor to transform raw HTML data files into a structured CSV format and Power BI Desktop for connecting to CSV files.
- Data Modeling: Power BI Desktop for building a relational data model to support analytical queries and reporting.
- Calculations and Measures: Utilize DAX (Data Analysis Expressions) within Power BI Desktop to create calculated columns and measures for deriving insights from the data.
- Dashboard Design: Design interactive dashboards within Power BI Desktop to visualize key metrics and facilitate data-driven decision-making for district education stakeholders.

## METHODOLOGY - Extraction, Transformation and Loading (ETL)
I've included YouTube videos explaining the details of how the raw data was extracted from tables in HTML files, transformed and loaded into CSV files in Excel Query Editor and lastly into Power BI. [Click here to access it](https://youtube.com/playlist?list=PLu51iz8trDWIOtUail_pcpbFVIswaYZ61&si=pksjVzRPjVR68NgA)

### Data Model
<img src="img/candidalysis-data-model.png" alt="candidiasis data model" style="width:100%;"/>

### DAX USED IN CREATING MEASURES 
Various DAX measures were created to calculate key performance indicators (KPIs) such as enrollment, exam attendance, subject grades, and aggregate scores. These measures enable precise analysis and insights generation.
  - **Enrolment in Junior High School 3**: 
    - <img src="img/candidalysis-total-candidates.png" alt="Total Candidates" />
    - *Enrolment = [Total No. students]*
  - **Number of candidates registered**:
     - *Candidates Registered = [Total No. students]*
  - **Number of candidates present during examination**:
    <img src="img/candidalysis-candidates-present.png" alt="Candidates Present During Examination" />
  - **Candidates Obtaining Grades 1 to 3 in the various subjects**:
      - => *Candidates Obtaining Grades 1- 3 = 
      CALCULATE(
          [Total No. students], 
          results[grades] >= 1 && results[grades] <= 3
      )*
   - **Number of candidates obtaining aggregates 6**:
       - => *Aggregates 6 = 
      CALCULATE(
          [Total No. students], 
          results[aggregates] = 6
      )*
   - **% Pass at 30**:
       - => *% Pass @ 30 = 
            DIVIDE(
                (
                    [Aggregates 6] + 
                    [Aggregates 7 - 15] +
                    [Aggregates 16 - 24] +
                    [Aggregates 25 - 30]
                ),
                [Exams Attendance Count (Present)]
            )*
## Insights Derived from Data Analysis
I have captured the insights derived from the data analysis process in a YouTube playlist [Click here](https://youtu.be/APqgIxjPgWQ). You can also access power bi file (candidalysis.pbix) for your perusal. [Click here](https://app.powerbi.com/groups/me/reports/bdf09ea1-0687-4fcd-a524-eb7830a0582e?ctid=104d8048-fd0c-43d5-a630-fc629e5dab59&pbi_source=linkShare&bookmarkGuid=8b719650-cf33-449a-b360-ae1474d5b165)

## Challenges
Challenges encountered in the project included data quality issues and performance optimization. These challenges were addressed through thorough data cleaning, performance testing and optimization.

## Recommendations
To address challenges faced during the project:
  -  Thorough data cleaning was conducted to address data quality issues and ensure consistency.
  -  Performance testing and optimization techniques were employed to enhance the speed and efficiency of Power BI reports and dashboards.
