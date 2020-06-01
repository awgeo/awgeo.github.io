---
title: "FlightHistory - a project in Tableau"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - jupyter_notebooks
  - tableau
---

Looking for a good dataset to play with in Tableau, I got a hold of my partner's flight history as Cabin Crew for Virgin Atlantic. It's a fascinating data set, documenting 700 international flights over seven years (on which I've bagged myself a few spare seats!).

### Data preparation

These Jupyter Notebooks describe the data preparation workflow using Python and Pandas before we can plot and analyse the data. The data is provided in two parts. First, data spanning Oct 2012 - Oct 2019 are provided in a series of Excel files ("Historical Crew Data"). Note that, where a flight runs over midnight GMT, its data spans two rows. A key step in this workflow is to keep just one row per flight, ensuring we carry over the correct flight dates, times, block hours, etc.

Second, more recent but less detailed flight data (up to end-March 2020) is parsed from an iCalendar (.iCal) file, in which basic flight information is recorded in a consistent manner. The two data sets are combined and reconciled, along with additional data from a third party data source, including geographical information (including airport lat/long) and distances calculated between origin/destination airports.

The final time-series data (output to 'flight_history_combined.xlsx') allows us to filter and categorise data on aircraft type, airport code, city, country, distance, flight time, shifts/blocks and roster periods.

### Data vizualisation

Full set of interactive plots published on <a href="https://public.tableau.com/profile/alan.wilson7526#!/" target="_blank">my Tableau Public profile</a>.

<b>Examples</b>

Number of flights to each US-Carribean destination per year:

<img src="flighthistory_us-destinations.PNG" alt="US and Carribean fights"

Number of flights per aircraft type:

<img src="flighthistory_flights-per-aircraft-type.PNG" alt="Flights per aircraft type"