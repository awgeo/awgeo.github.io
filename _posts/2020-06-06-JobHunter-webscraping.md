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

The challenge was to scrape job listing results from several energy company career sites, then amalgamate the results into a single, searchable DataFrame. Scraping data from dynamic web pages is, it seems, no easy task and the code is difficult to maintain. But it's been a good learning experience.

New to web-scraping, I quickly realised these career sites are difficult to scrape for a number of reasons, least not because the search results are paginated (e.g. 25 results per page). The script must interact with each page - navigating between them and - using intentional pauses - waiting for the new set of results to loaded from the server. Each time, the script has to iterate over a set of results and append each record to a DataFrame. Also, as the content is dynamic and prone to change, the script is not robust and can easily break. Of course, each site is entirely unique and the format of each job listing can be inconsistent.

    ``` python
	from selenium import webdriver
	driver = webdriver.Chrome("C:/webdrivers/chromedriver.exe")
	
	# Navigate to search page
    url = "https://jobs.halliburton.com/search/?q=&sortColumn=referencedate&sortDirection=desc&startrow="
    driver.get(url)

    # Find the number of results returned by search
    num_results = driver.find_element_by_xpath("""//*[@id="content"]/div[2]/div/div[4]/div/div[1]/div/div/div/span[1]/b[2]""")
	```

After spending some time inspecting the HTML source code of several career sites, I decided to start with the Haliburton and BP sites as these are structured such that I found it <i>relatively</i> easy to locate elements of the page required. That said, just looking at the code block above, you have to dig pretty deep to access the first piece of information you need: the element that tells you the "number of results returned by search".

<a href="https://github.com/awgeo/JobHunter" target="_blank">My script</a> uses ChromeDriver and Selenium to perform webscraping of the Hallibuton and BP career sites. It retreives and parses out each job's headline information (role, location, etc.), but not the detailed content behind each listing. My idea was to create a list of keywords to search for, one list for job titles and one list for locations. The final, amalgamated dataframe could then be filtered on these search criteria. The hyperlink to each job listing should be maintained and made clickable. All do-able, but knowing how fragile this code is, I think I'll leave it at this for now.

UPDATE: already, just a few months after first working on this, the BP career site has changed enough to break the script. Rather than diving back into hunt down "elements by xpath", I think I'll save my web-scraping efforts for a more manageable project!

Speaking of which, I enjoyed working through this <a href="https://notebooks.azure.com/awgeo/projects/trump-lies" target="_blank">Trump Lies project</a> that uses an alternative web scraping package, Beautiful Soup. The tutorial is by Kevin Markham, the guy behind the <a href="https://www.youtube.com/user/dataschool" target="_blank">DataSchool Youtube channel</a> which is a great resource.