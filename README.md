# Basic-pandas
```python
import pandas as pd
movies = pd.read_csv("movies.csv")
ratings = pd.read_csv("ratings.csv")
ratings5 = ratings[ratings["rating"] == 5.0]
next = (
 ratings5
  .groupby("movieId")
  .size()
  .reset_index( name = "count5")
)
sumup = (
    next
    .sort_values("count5", ascending = False )
    .head(1)
)
sumup
power = pd.read_csv("power.csv")
power_baltic = power[power["country"].isin (["Latvia", "Lithuania", "Estonia"])]
poweryear = power_baltic[
    (power_baltic["year"] >= 2005) &
    (power_baltic["year"] <= 2010)
]
categories = [4, 12, 21]
power_baltic = power_baltic[power_baltic["category"]
    .isin (categories)]
power_baltic = power_baltic[power_baltic["quantity"] >= 0]
total_consumption = power_baltic["quantity"].sum()
