---
title: "Post: Standard"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Post Formats
  - readability
  - standard
---

<div data-iframe-width="300" data-iframe-height="540" data-share-badge-id="3fc48705-b81d-4d25-bf1c-7f2df0c8bb39" data-share-badge-host="https://www.youracclaim.com"></div><script type="text/javascript" async src="//cdn.youracclaim.com/assets/utilities/embed.js"></script>

Interested to learn more about data warehousing, I stumbled upon Snowflake (not knowing whether it was widely used) and joined one their "Zero to Snowflake in 90 minutes" hands-on labs. Then, after reading a comment on DataCamp Data Engineering course that Snowflake was "disrupting the data warehouse industry", I decided to invest some more time in it. I've now completed the "Hands On Snowflake - WebUI Essentials" certification, which involves submitting a short screenshare video, talking through your results.

The course covered: User Roles, Navigation, Creating Database Objects, Virtual Warehouse creation and configuration, loading and querying CSV and JSON data.

It gives a good overview of the ETL process in Snowflake, moving the data between tables and transforming it en-route. In Snowflake, a "warehouse" refers to the compute power applied to process the processing data and not to the data store. Each warehouse has a single cluster of servers, and the number of servers in that cluster vary based on the warehouse size designation.

It's been interesting see how you would work with "elastic data warehousing". If your Snowflake account is Multi-Cluster then you have options to set the number Clusters (min/max) and Scaling Policy. Also, the course taught how to set an AWS S3 bucket up as a stage, from which you can transform data while loading from its persistent file location (avoiding an ETL to transfer the data and the need for an '_ingest' table).

Snowflake's "variant" data format is interesting, as it lets you load semi-structured data (like JSON) to a single record then extract key-value pairs as needed, saving the need for a more complex, normalized database design. 

I'd like to look into semi-structured formats, like those that Snowflake can handle: XML, JSON, Parquet, Avro and Orc.

Next up: Snowflake's Level Up courses.