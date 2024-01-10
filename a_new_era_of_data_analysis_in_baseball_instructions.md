# [Project: A New Era of Data Analysis in Baseball](https://app.datacamp.com/learn/projects/250)

Original Environment:
- seaborn: 0.8.1
- pandas: 0.22.0
- matplotlib: 2.2.2


### Task 1: Instructions
Load the CSV files, which hold the Statcast data for each player, into pandas DataFrames.

- Load `data/judge.csv` into a DataFrame and assign it to the variable `judge`.
- Load `data/stanton.csv` into a DataFrame and assign it to the variable `stanton`.

**Good to know**

This Project requires that you know your way around Python, pandas, and data visualization. We recommend the following courses as prerequisites:

- Intermediate Python
- Introduction to Data Visualization with Matplotlib
- Introduction to Data Visualization with Seaborn

[MLB.com's Statcast glossary](https://www.mlb.com/glossary/statcast) (MLB stands for Major League Baseball) may be helpful at various points throughout the Project. Through accessible text and video, they explain baseball concepts in more detail than the Project Notebook. Links to specific glossary pages will be provided throughout the Project.

### Task 2: Instructions
Display the last five rows of the judge DataFrame.

Use pandas' `tail` method to display the last five rows of judge.
The last five rows of the judge DataFrame are displayed instead of the first five because they contain more interesting data.

**Helpful links:**

- pandas' tail method ([documentation](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.tail.html))

### Task 3: Instructions
Isolate each player's batted ball events for the 2017 season.

- Filter `judge` to include pitches from `2017` only and select the `events` column. Store the result in a variable called `judge_events_2017`.
- Using the `value_counts` method, print out the count of unique values for `judge_events_2017`.
- Filter `stanton` to include pitches from 2017 only and select the `events` column. Store the result in a variable called `stanton_events_2017`.
- Using the `value_counts` method, print out the count of unique values for `stanton_events_2017`.

**Helpful links:**

- pandas' value_counts method ([documentation](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.value_counts.html))


### Task 4: Instructions
Isolate each player's home runs then plot exit velocity vs. launch angle.

- Filter the `judge` and `stanton` DataFrames to include home runs only.
- Create a figure using seaborn's `regplot` function with two scatter plots of launch speed vs. launch angle, one for each player's home runs.
- Create a figure using seaborn's `kdeplot` function with two KDE plots of launch speed vs. launch angle, one for each player's home runs.

Exit velocity is also known as launch speed, where `launch_speed` is the name of the column in each file.

**Helpful links:**

- seaborn's `regplot` function ([documentation](https://seaborn.pydata.org/generated/seaborn.regplot.html))
- seaborn's `kdeplot` function ([documentation](https://seaborn.pydata.org/generated/seaborn.kdeplot.html))


### Task 5: Instructions
Plot the pitch velocities of each player's home runs on box plots.

- Concatenate judge_hr and stanton_hr using pandas' concat function and store the result in a variable called judge_stanton_hr.
- Create a boxplot using seaborn's boxplot function that describes the pitch velocity of each player's home runs. Make the color argument 'tab:blue'.
- Pitch velocity is also known as release speed, where release_speed is the name of the column in each file.

**Helpful links:**

- pandas' concat function ([documentation](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.concat.html))
- seaborn's boxplot function ([documentation](https://seaborn.pydata.org/generated/seaborn.boxplot.html))

### Task 6: Instructions
Create a function that returns the x-coordinate of a pitch zone.

- Return the x-coordinate for the left third of strike zone.
- Return the x-coordinate for the middle third of strike zone.
- Return the x-coordinate for the right third of strike zone.

While you should ignore zones 11, 12, 13, and 14 for this plotting task, setting up conditionals to filter these out now isn't necessary. That will come in an upcoming task!

`zone` is the name of the column that holds each pitch's zone data.

It may be helpful to draw the zone and label the x- and y-coordinates by hand.

### Task 7: Instructions
Create a function that returns the y-coordinate of a pitch zone.

- Return the y-coordinate for the upper third of strike zone.
- Return the y-coordinate for the middle third of strike zone.
- Return the y-coordinate for the lower third of strike zone.

While you should ignore zones 11, 12, 13, and 14 for this plotting task, setting up conditionals to filter these out now isn't necessary. That will come in an upcoming task!

`zone` is the name of the column that holds each pitch's zone data.

It may be helpful to draw the zone and label the x- and y-coordinates by hand.

### Task 8: Instructions
Assign Cartesian coordinates to the strike zone and plot pitches that resulted in Judge home runs as a 2D histogram.

- Apply `assign_x_coord` to `judge_strike_hr` to create a new column called `zone_x`.
- Apply `assign_y_coord` to `judge_strike_hr` to create a new column called `zone_y`.
- Plot Judge's home run zone as a 2D histogram (using matplotlib's hist2d function) with a colorbar.

Helpful links:

- pandas' apply method ([documentation](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.apply.html))
- How to use pandas' apply method ([StackOverflow answer](https://stackoverflow.com/questions/27041724/using-conditional-to-generate-new-column-in-pandas-dataframe))
- matplotlib's hist2d function ([documentation](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.hist2d.html))


### Task 9: Instructions
Assign Cartesian coordinates to the strike zone and plot pitches that resulted in Stanton home runs as a 2D histogram.

- Apply `assign_x_coord` to `stanton_strike_hr` to create a new column called `zone_x`.
- Apply `assign_y_coord` to `stanton_strike_hr` to create a new column called `zone_y`.
- Plot Stanton's home run zone as a 2D histogram (using matplotlib's hist2d function) with a colorbar.

### Task 10: Instructions
Answer the following question: "Should opposing pitchers be wary of Aaron Judge and Giancarlo Stanton?"

- Store a Boolean value (`True` or `False`) in should_pitchers_be_scared.

These editorial images ([Judge](https://www.gettyimages.ca/photos/aaron-judge?sort=mostpopular&mediatype=photography&phrase=aaron%20judge&family=editorial), [Stanton](https://www.gettyimages.com/photos/giancarlo-stanton?sort=mostpopular&mediatype=photography&phrase=giancarlo%20stanton&family=editorial)) from Getty Images are awesome. The best are the ones with each player next to normal sized humans.

If you'd like more Statcast content to digest, this video ([A culmination of special Statcast records in 2017](https://www.youtube.com/watch?v=tzPKlQXo6hk) from MLB's YouTube channel) and this article ([Major League Baseball's Statcast Can Break Sabermetrics](https://deadspin.com/major-league-baseballs-statcast-can-break-sabermetrics-1820987737) by Emma Baccellieri) are excellent.