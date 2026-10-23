# Analyzing Students' Mental Health — SQL Project

## Overview

This project uses PostgreSQL to analyze student mental health survey data from a Japanese international university.

The analysis focuses on international students and examines how their length of stay relates to depression, social connectedness and acculturative stress.

Completed as part of DataCamp's guided *Analyzing Students' Mental Health* project.

## Technologies

- PostgreSQL
- SQL
- Jupyter Notebook

## Dataset

The dataset contains 286 student records and includes information about student demographics, academic background, length of stay and mental health indicators.

Key columns used:

| Column | Description |
|---|---|
| `inter_dom` | International or domestic student classification |
| `stay` | Length of stay in years |
| `todep` | Depression score (PHQ-9) |
| `tosc` | Social connectedness score (SCS) |
| `toas` | Acculturative stress score (ASISS) |

## SQL Implementation

The following PostgreSQL query analyzes international students by length of stay:

```sql
SELECT
    stay,
    COUNT(*) AS count_int,
    ROUND(AVG(todep), 2) AS average_phq,
    ROUND(AVG(tosc), 2) AS average_scs,
    ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC
LIMIT 9;
```

## SQL Concepts Applied

- `SELECT` — Retrieve the required columns and calculated values.
- `WHERE` — Filter international student records.
- `GROUP BY` — Group students by length of stay.
- `COUNT` — Calculate the number of students in each group.
- `AVG` — Calculate average mental health scores.
- `ROUND` — Format averages to two decimal places.
- `ORDER BY` — Sort results by length of stay.
- `LIMIT` — Restrict the output to nine groups.

## Project Outcome

Constructed a SQL aggregation query to summarize mental health indicators among international students across different lengths of stay.

The project demonstrates foundational SQL skills in filtering, grouping, aggregation and structured data analysis.

## Project Files

- `notebook.ipynb` — Jupyter notebook containing the SQL analysis.
- `students.csv` — Student survey dataset, if redistribution is permitted.
- `mentalhealth.jpg` — Notebook illustration, if reuse is permitted.

## Attribution

This project was completed through DataCamp's guided *Analyzing Students' Mental Health* project.

Original project: https://app.datacamp.com/learn/projects/analyzing_students_mental_health

The SQL query reflects my completed project work.
