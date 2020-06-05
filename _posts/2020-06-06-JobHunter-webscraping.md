---
title: "JobHunter - web-scraping career sites with Selenium"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - web-scraping
  - selenium
  - chromedriver
  - beautifulsoup
---

This (overly ambitious) challenge was to scrape job listing results from several oil company career sites, then amalgamate the results into a single, searchable DataFrame. Scraping data from dynamic web pages is, it seems, no easy task and the code is difficult to maintain. But it's been a good learning experience.

New to web scraping, I quickly realised these sites are difficult to scrape for a number of reasons - least not because the search results are paginated (e.g. 25 results per page). The script must interact with each page - navigating to each page then (using intentional pauses) waiting for the new set of results to loaded from the server database. Each time, the script has to iterate over a set of results, and append each record to a DataFrame. Also, as the content is dynamic and prone to change, the script is not robust and can easily break. Of course, each site is entirely unique and the format of each job listing can be inconsistent.

```python
# Selenium WebDriver uses ChromeDriver to nagivate webpages
driver = webdriver.Chrome("C:/webdrivers/chromedriver.exe")

# Calculate number of pages to iterate over (max_page_num)
url = "https://jobs.halliburton.com/search/?q=&sortColumn=referencedate&sortDirection=desc&startrow="
driver.get(url)```

My <a href="https://github.com/awgeo/JobHunter">script</a> uses ChromeDriver and Selenium to perform webscraping of the Hallibuton and BP career sites. After spending some time inspecting the HTML source code of several career sites, I select these two sites as they are structured such that I found it <i>relatively</i> easy to access the elements of the page required. The stript retreives and parses out each job's headline information (role, location, etc.), but not the detailed content behind each listing.

My idea was to create a list of keywords to search for, one list for job titles and one list for locations. The final, amalgamated dataframe could then be filtered on these search criteria. The hyperlink to each job listing should be maintained and made clickable. All do-able, but knowing how fragile this code is, I think I'll leeave it at this for now.

Update: already, just a few months after first working on this, the BP career site has changed enough to break the script. Rather than diving back into hunt down "elements by xpath", I think I'll save my web-scraping efforts for a more manageable project!

Speaking of which, I enjoyed working through this <a href="https://notebooks.azure.com/awgeo/projects/trump-lies" target="_blank">Trump's Lies project</a> that uses an alternative web scraping package, Beautiful Soup. The tutorial is by Kevin Markham, the guy behind the <a href="https://www.youtube.com/user/dataschool" target="_blank">DataSchool Youtube channel</a> which is a great resource.