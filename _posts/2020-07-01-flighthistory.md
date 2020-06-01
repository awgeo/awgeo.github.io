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

<div class='tableauPlaceholder' id='viz1591025035413' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ca&#47;CabinCrewFlightHistory&#47;FlightHistory&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='CabinCrewFlightHistory&#47;FlightHistory' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ca&#47;CabinCrewFlightHistory&#47;FlightHistory&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1591025035413');                    var vizElement = divElement.getElementsByTagName('object')[0];                    vizElement.style.width='1016px';vizElement.style.height='991px';                    var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>