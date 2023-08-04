# Interactive World CO2 Dashboard

I have used the panel for the dashboard.So you can  go to Panel website and follow the intructions.

Basiclly go to your project file and run terminal;

> python 3 -m venv ./


> source bin/activate


> pip3 install hvplot jupyterlab


> deactivate


> pip3 install panel



As a data source I have used the Our World In Data source on GitHub, OWI/co2-data

@thu-vu92 helped me with the all codes, I made some changes.

In order to run the panel ;

> panel serve dashboard.ipynb

![](dashboard.png)


CO2 Data Analysis and Dashboard Documentation

This script performs data analysis and visualization on CO2 emissions data using the Pandas, NumPy, Panel, and HoloViews libraries. It creates an interactive dashboard to explore and understand the CO2 emissions of various countries over time.

Data Retrieval:

The script first imports the necessary libraries, including Pandas, NumPy, Panel, and HoloViews. It then reads the CO2 emissions data from a CSV file hosted on GitHub using Pandas' read_csv function.

Data Analysis:

After loading the data into a DataFrame df, some data manipulation is performed:

    A new interactive DataFrame idf is created from df using Panel's interactive() function.

    A new column year_end is added to df, which is initialized with the same values as the existing year column.

Dashboard Widgets:

Next, several interactive widgets are defined using Panel:

    year_slider: An IntRangeSlider widget allowing users to select a range of years for data filtering.

    yaxis_co2: A RadioButtonGroup widget for users to select the Y-axis measure for the CO2 plot.

    yaxis_co2_source: Another RadioButtonGroup widget to select the Y-axis measure for the CO2 source bar plot.

Data Visualization:

    A line plot (co2_plot) is created to show the CO2 emissions of European countries over time using HoloViews' hvplot. The co2_pipeline DataFrame is used to compute the mean CO2 emissions for each year and country.

    A tabulator widget (co2_table) is created using Panel's Tabulator function to display a table of the CO2 emissions data for European countries, allowing pagination and customizing the page size.

    A scatter plot (co2_vs_gdp_scatterplot_pipeline) is created to visualize the relationship between CO2 emissions and GDP for non-European countries.

    A bar plot (co2_source_bar_plot) is created to display the CO2 source breakdown (coal, oil, gas) by continent for a specific year. The co2_source_bar_pipeline DataFrame is used to compute the sum of CO2 sources for each continent in a given year.

Dashboard Layout:

The script defines a dashboard layout using Panel's FastListTemplate. The layout includes a title, sidebar, and main sections. In the sidebar, the year_slider widget is displayed. The main section consists of two rows: the first row displays the co2_plot and yaxis_co2 widget, and the second row displays the co2_source_bar_plot, yaxis_co2_source, and co2_table widgets.

Dashboard Display:

The dashboard is rendered and made available to users through a server using the template.servable() method.

Usage:

Users can interact with the dashboard by adjusting the year range using the year_slider, choosing the Y-axis measure for the CO2 plot using yaxis_co2, and selecting the Y-axis measure for the CO2 source bar plot using yaxis_co2_source.

Note:

The script may generate some FutureWarnings related to iterating over a groupby with a grouper equal to a list of length 1. These warnings can be ignored for the time being, as they do not affect the functionality of the dashboard.

Please make sure that the earth.png file is present in the same directory as the script, as it is used as an image in the sidebar of the dashboard.

This documentation provides an overview of the CO2 data analysis and visualization script and the interactive dashboard it creates to explore the CO2 emissions data.
