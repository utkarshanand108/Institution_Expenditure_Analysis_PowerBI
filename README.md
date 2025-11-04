# DataScienceCourse3_Assignment3
**Institution & Expenditure Analysis — DS PGC Course 3 Assignment 3**

---

## 📘 Assignment Overview
This assignment analyses institutional performance and public expenditure datasets using **Power BI**.  
It uses two datasets: **Expenditure** (unpivoted years → Year & Expenditure) and **Data** (institution metrics).  
Deliverable: a PDF (Word → PDF) containing screenshots and steps for each task.

---

## 🧩 Tasks Summary
1. Average public expenditure in **2005** (public type).  
2. Total publications for institutions in the **United Kingdom**.  
3. Filter and show institutions with **world_rank < 100**.  
4. Total expenditure across all years per **country**.  
5. DAX to compute **total score ignoring year filters**.  
6. Growth in expenditure for **Austria** from 1995 → 2000 (absolute + %).  
7. Format expenditure as **currency** with zero decimals.  
8. Visual: total expenditure per country (bar / column).  
9. Report pages (a–d):  
   - (a) Patents by country → quality_of_faculty (Decomposition Tree)  
   - (b) Q&A: total publications & citations for USA (table + bar chart)  
   - (c) Top 5 institutions by world_rank (Table: institution, country, score, national_rank)  
   - (d) Distribution of direct_expenditure_type in **2011**, highlight OECD Average  
10. Create workspace **“Institution Analysis”** and schedule refresh at **6:00 AM daily** (Power BI Service).

---

## 🧰 Tools & Key Steps
- **Power BI Desktop** — Power Query Editor: *Unpivot* year columns → Year / Expenditure  
- **Power Query** — Remove duplicates; set Year → Whole Number; Expenditure → Decimal  
- **DAX measures (examples)**:
  ```DAX
  Avg Public Expenditure 2005 :=
    AVERAGEX(
      FILTER(Expenditure, Expenditure[Year] = 2005 && Expenditure[direct_expenditure_type] = "public"),
      Expenditure[Expenditure]
    )

  Total Publications (UK) :=
    CALCULATE(SUM(Data[publications]), Data[country] = "United Kingdom")

  Total Score (All Years, Ignore Year Filters) :=
    CALCULATE(SUM(Data[score]), ALL(Data[year]))
  ```
- **Visuals** — Cards, Tables, Clustered Columns, Decomposition Tree, Q&A Visuals  
- **Power BI Service** — Publish PBIX → Workspace *Institution Analysis* → Schedule Refresh (6:00 AM)

---

## 📂 Files Included
- `DataScienceCourse3Assignmen3Question.pdf` — Assignment brief  
- `DataScienceCourse3Assignmen3Solution.pdf` — Completed Power BI solution with steps & visuals

---

## 🧭 How to Review
1. Download the solution PDF.  
2. Open Power BI Desktop → Transform data → Recreate steps.  
3. Check visuals, DAX formulas, and filters match screenshots in the solution file.

---

## 👤 Author
**Utkarsh Anand**  
DS PGC Course 3 — Internshala Trainings
