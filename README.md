# F1 | From grid to finish

**Project brief.** How often did the polesitter win, and which circuits saw the biggest changes between starting and finishing position? Start with Grand Prix results from 2014–2023. Exclude sprints.

## Data and checks

Use the [Kaggle F1 World Championship dataset](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020). Join results to races, drivers, circuits and status. Keep one row per raceId and driverId. Record the download date, seasons present, missing grid positions and duplicate keys. Check that joins preserve the result row count.

| Metric | Definition |
| --- | --- |
| Pole-to-win rate | Count races where grid 1 won divided by races with exactly one grid 1 starter and one recorded winner. Include polesitter retirements. |
| Places gained | Grid minus classified finish position for drivers with a positive grid and a numeric finish position. Positive means the driver gained places. |
| Circuit movement | Average absolute places gained among eligible drivers. Show eligible driver starts and race count beside each circuit. This measures net movement between start and finish, not overtakes. |

## Build sequence

1. Import CSVs, inspect keys and hand-check one Grand Prix against its result rows.
2. Start with Mode if CSV upload is available in the account. Build a season filter, pole conversion KPI, circuit ranking and drill-down table of driver starts and finishes.
3. For the Power BI route, import the CSVs directly for the first PBIX. To practice SQL Server, load the same CSVs into staging tables and connect Power BI to a reporting view. Compare the row counts and KPIs between routes.
4. Publish a screenshot, metric definitions and three findings with their season, sample size and limitations. Keep findings pending until calculated.
