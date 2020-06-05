---
title: "Snowflake Data Warehouse: WebUI Essentials Certification"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - snowflake
  - data_warehouse
  - cloud
---

I thought I'd check out <a href="https://www.snowflake.com/about/">Snowflake Cloud Data Warehouse</a> after reading on a DataCamp Data Engineering course that it was "disrupting the data warehouse industry". I first completed the "Zero to Snowflake in 90 minutes" hands-on lab, and have just now completed the first of their certifications:  "Hands On Snowflake - WebUI Essentials".

<div data-iframe-width="600" data-iframe-height="270" data-share-badge-id="3fc48705-b81d-4d25-bf1c-7f2df0c8bb39" data-share-badge-host="https://www.youracclaim.com"></div><script type="text/javascript" async src="//cdn.youracclaim.com/assets/utilities/embed.js"></script>

The course gives a good introduction to <a href="https://www.snowflake.com/data-warehousing-glossary/data-warehousing/">data warehousing</a> and explains the ETL process in Snowflake, moving the data between tables and transforming it en-route. It covered: User Roles, Navigation, Creating Database Objects, Virtual Warehouse creation and configuration, loading and querying CSV and JSON data.

In Snowflake, a "warehouse" refers to the compute power applied to process the processing data and not to the data store. Each warehouse has  single cluster of servers, and the number of servers in that cluster vary based on the warehouse size designation.

It's been interesting see how to work with "elastic data warehousing". If your Snowflake account is Multi-Cluster then you have options to set the number Clusters (min/max) and Scaling Policy. Also, the course taught how to set an AWS S3 bucket up as a stage, from which you can transform data while loading from its persistent file location (avoiding an ETL to transfer the data and the need for an '_ingest' table).

Snowflake's "variant" data format is interesting, as it lets you load semi-structured data (like JSON) to a single record then extract key-value pairs as needed, saving the need for a more complex, normalized database design. 

I plan on spending some more time looking into the different semi-structured formats that Snowflake can handle: XML, JSON, Parquet, Avro and Orc.

Next up is Snowflake's Level Up courses and, ultimately, their SnowPro Certification.