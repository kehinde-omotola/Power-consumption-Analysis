# Morocco Electricity Consumption Analysis
## Project overview
This project explores electricity consumption readings across three geographical zones in Morocco. The organisation records readings every 10 minutes, together with environmental measurements. The aim is to understand how the readings change over time, how the three zones compare, and whether temperature, humidity and wind speed move alongside electricity readings.
I used Excel, Power Query and Power BI for this project.
# Business problem
The organisation has a large amount of electricity and environmental data, but needs clear information to support energy planning. This analysis focuses on:
What patterns can be seen across the three zones?
During which hours and days do readings tend to be highest and lowest?
How do readings change across the months?
Are temperature, humidity and wind speed associated with the readings?
Which zone records the highest and lowest readings?
How can historical patterns support better energy management?

### Tools used
Excel: supporting inspection and analysis.
Power Query: data cleaning, preparation, time fields and unpivoting the zone columns.
Power BI: data model, measures, interactive visuals and dashboard.
## Data preparation
The preparation workflow in Power Query included:
Importing the main CSV file.
Checking the column structure and data types.
Converting `Datetime` to a date/time data type.
Creating time fields such as year, month, month number, date, hour, weekday and week number.
Creating a `Date` column from `Datetime` in the original consumption table.
Creating a `Zone_Comparison` query from the original data.
A separate `DateTable` was created in Power BI. It connects to the `Date` column in both consumption tables through one-to-many, single-direction relationships.

### Data model
The model contains three main tables:
`DateTable`: calendar dates and date attributes used for filtering.
`PowerConsumption`: original wide table, used for overall measures and environmental analysis.
`Zone_Comparison`: long-format table with one row per timestamp and zone, used for zone comparisons.
The Date Table filters both consumption tables. The two consumption tables are not joined directly.
# Dashboard
The Power BI report has two pages.
# Page 1 – Consumption Overview
<img width="599" height="341" alt="Consumption Overview" src="https://github.com/user-attachments/assets/c1a1d2c1-7f6d-4422-8676-c25d58f22ae3" />

This page includes five KPI cards:
Average Zone 1 reading
Average Zone 2 reading
Average Zone 3 reading
Average combined reading
Total observations
It also includes visuals for:
Average reading by zone
Electricity reading trend over time
Average hourly reading
Average reading by weekday
Average reading by month
Hourly reading patterns across the three zones
# Page 2 – Environmental & Zone Analysis

<img width="598" height="335" alt="Environmental & zone analysis" src="https://github.com/user-attachments/assets/0f3625c7-936b-4d50-b1a6-5e34f8f38415" />

This page includes average humidity, average temperature and average wind speed cards, as well as:
Temperature vs electricity reading scatter plot
Humidity vs electricity reading scatter plot
Wind speed vs electricity reading scatter plot
Zone performance matrix
Monthly reading by zone
Hourly reading by zone

Measure	Value
Average Zone 1 reading	32,344.97
Average Zone 2 reading	21,042.51
Average Zone 3 reading	17,835.41
Average combined reading	71,222.89
Total observations	52,416
Average humidity	68.26
Average temperature	18.81
Average wind speed	1.96
The average combined reading is the sum of the three displayed zone averages. It is not confirmed energy consumed during a 10-minute interval.
Zone performance
Zone	Average reading	Minimum reading	Maximum reading
Zone 1	32,344.97	13,895.70	52,204.40
Zone 2	21,042.51	8,580.06	37,438.85
Zone 3	17,835.41	5,935.77	47,598.35
## Initial findings
Based on the values and patterns currently visible in the dashboard:
Zone 1 has the highest average recorded reading.
Zone 3 has the lowest average recorded reading.
Zone 1 has the highest maximum reading shown in the zone matrix.
The monthly chart suggests that readings rise toward the middle of the year, with the highest bars around July and August, then fall later in the year.
The hourly chart suggests lower readings in the early morning and a higher period around the evening, with the visible peak near 20:00.
The weekday chart looks fairly consistent, although Sunday appears lower than most other days.
The environmental scatter plots need numerical correlation results before the strength or direction of any association can be reported.
These time-based findings are visual observations. Exact peak and lowest values should be taken from validated measures before being quoted as final results.
## Recommendations
Use hourly patterns for demand planning. Confirm the peak and low hours from the underlying data, then use them to support demand monitoring and operational planning.
Review Zone 1 demand. Since Zone 1 has the highest average reading, investigate the local factors that may explain its higher readings before choosing an intervention.
Investigate unusual readings in Zone 3. Its average is the lowest, but its displayed maximum is relatively high. Review the observations behind the extremes to distinguish genuine variation from possible data issues.

## Conclusion
This project turns the original 10-minute records into an interactive view of electricity readings across three zones. The current dashboard shows that Zone 1 has the highest average reading and Zone 3 the lowest. It also provides a way to explore hourly, weekday and monthly patterns, and to investigate how environmental measurements sit alongside electricity readings.
