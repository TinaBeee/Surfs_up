## Advanced Databases
Analysis of sqlite dataset in Jupyter Notebook and use of Flask to develop a simple web application

### Resources
- Data Sources: hawaii.sqlite
- Software: Visual Studio Code 1.60.0, Jupyter Notebook 6.3.0, Sqlalchemy library, Pandas library, Matplotlib library, Numpy library

### Overview of the Analysis
Analysis of hawaii.sqlite dataset, which contains two tables - one for individual temperature measurements, the other with location information for individual measuring stations. The temperature measurements were collected over a period of more than seven years, and in this analysis temperature measurements for the month of June and December throughout the years were filtered.

### Results
After filtering the June temperature data, the summary statistics look as follows (temperature in Fahrenheit)

<img src="https://user-images.githubusercontent.com/90064437/146657878-9f8809f5-68c6-4416-9ede-94551a7c523d.png" width="200">


The summary statistics for December data look at follows (temperature in Fahrenheit):

<img src="https://user-images.githubusercontent.com/90064437/146657910-1e3359f3-77c1-4251-bc3a-d64485b0f093.png" width="200">

## Summary
The data analysis shows the difference in temperatures between June and December, with June predictably being warmer overall than December. 
Further analysis could be done to analyze the precipitation data for those two months with the following query: `session.query(Measurement).filter(extract("month", Measurement.prcp)==6/12)`.

Additionally, we could determine whether there are significant differences in temperature measurements between the nine measurment stations. For one example station, the filter query would look as follows: `session.query(Measurement).filter(extract("month", Measurement.date)==6/12, Measurement.station == "USC00519397")`.

We could query the results for all nine stations to determine if there are significant differences between the stations.
