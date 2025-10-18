# Programming Languages Popularity Analysis

A comprehensive data analysis project examining programming language trends over time using Stack Overflow post data.

## Overview

This project analyzes the popularity of various programming languages from 2008-2020 based on Stack Overflow post frequency. The analysis includes data exploration, cleaning, manipulation, and visualization using Python's pandas and matplotlib libraries.

## Features

- **Data Source**: Stack Overflow posts data queried by programming language tags
- **Languages Analyzed**: Java, C, C++, Python, C#, JavaScript, Assembly, PHP, Perl, Ruby, Visual Basic, Swift, R, Objective-C, Scratch, Go, and Delphi
- **Time Period**: 2008-2020 (144+ months of data)
- **Visualizations**: Time series plots, trend analysis, and rolling averages

## Files

- `Programming_Languages.ipynb` - Main Jupyter notebook with complete analysis
- `QueryResults.csv` - Sample dataset with programming language post counts
- `README.md` - This documentation file

## Key Insights

- **JavaScript** leads with the highest total posts (2,056,510+ in the full dataset)
- **Java** and **Python** maintain strong, consistent popularity
- Newer languages like **Swift** and **Go** show growth trends since their introduction
- The analysis reveals seasonal patterns and long-term trends in developer interest

## Notebook Structure

1. **Data Collection** - Instructions for obtaining fresh Stack Overflow data
2. **Data Exploration** - Basic statistics and data understanding
3. **Data Cleaning** - Date formatting and data type conversions
4. **Data Manipulation** - Pivot tables and data reshaping
5. **Data Visualization** - Time series plots and trend analysis

## Requirements

```python
import pandas as pd
import matplotlib.pyplot as plt
```

## Usage

1. Open `Programming_Languages.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells to execute the complete analysis
3. The notebook includes challenges and exercises for learning data analysis techniques

## Data Source

The original data can be obtained by running this SQL query on [Stack Exchange Data Explorer](https://data.stackexchange.com/stackoverflow/query/675441/popular-programming-languages-per-over-time-eversql-com):

```sql
select dateadd(month, datediff(month, 0, q.CreationDate), 0) m, TagName, count(*)
from PostTags pt
join Posts q on q.Id=pt.PostId
join Tags t on t.Id=pt.TagId
where TagName in ('java','c','c++','python','c#','javascript','assembly','php','perl','ruby','visual basic','swift','r','object-c','scratch','go','swift','delphi')
and q.CreationDate < dateadd(month, datediff(month, 0, getdate()), 0)
group by dateadd(month, datediff(month, 0, q.CreationDate), 0), TagName
order by dateadd(month, datediff(month, 0, q.CreationDate), 0)
```

## Recent Updates

- Fixed typo in "Data Visualization" section header
- Removed empty code cells for cleaner notebook structure
- Added sample CSV data file for immediate notebook execution
- Improved code formatting and documentation

## Learning Objectives

This project demonstrates:
- Data loading and exploration with pandas
- Data cleaning and preprocessing techniques
- Time series data manipulation
- Creating effective visualizations with matplotlib
- Trend analysis and pattern recognition
- Working with real-world datasets

Perfect for learning data analysis fundamentals and matplotlib visualization techniques!