---
layout: post
current: post
cover: assets/images/travel/3YearsOfTsaThroughput.png
navigation: True
title: Three Years of TSA Throughput Data
date: 2023-01-03 12:00:00
tags: travel
class: post-template
subclass: 'post'
logo: assets/images/ghost.png
author: mikelor
---

The photos above were taken almost three years apart. Both are of the Alaska Airlines lobby in SEA. The left one is from my March 22, 2020 flight to LAS, I was just one of the 7,642 passengers to be screened by TSA in SEA that day, a far cry from the 55,933 passengers screened on the same day one year prior. The one on the right is from my most recent trip through SEA on Christmas Day 2022 when 44,527 passengers were screened by TSA. 


How do I know this? Well, it turns out that the TSA publishes the number of passengers screened at all domestic airports on a regular basis. They make information available on their [Freedom of Information Act (FOIA) Reading Room website](https://www.tsa.gov/foia/readingroom). During the pandemic, as a sort of deranged therapy, I started tracking the TSA Throughput on a regular basis. This took a bit of work however, as the TSA only publishes their data in PDF format which makes it difficult to do any form of statistical analyis (more on this later).

Let's take a look at small animation of TSA Throughput for the entire country during the height of the pandemic (it's pretty depressing).

![TSA Throughput - All Airports](assets/images/travel/TsaThroughputAnimated.gif)

It's not hard to figure out when COVID came in full force. We went from roughly 2M passengers being screened on a daily basis to less than 100K on April 8th, 2020.
SEA would finally bottom out on April 8th, 2020 with just 2,564 passengers screened at all TSA checkpoints. Please note that this total does not include passengers who may be connecting in SEA as they usually do not need to go through TSA.


12/23 - 27,245

The graph below shows the number of passenger screened by TSA at SEA on a daily basis since January 1st, 2019. It shouldn't be hard to spot

I wanted to capture all the big announcements from this keynote in one spot, plus add a little commentary and takeaways. In another post I'm cataloging all of the announcements by Area and Product. You can checkout what this looks like at the end of the post. 

If you see something wrong, or missing, hit me up on [Mastodon](https://awscommunity.social/@mikelor/), [LinkedIn](https://linkedin.com/in/mlorengo/), or [Twitter](https://twitter.com/mikelor).

# The Intro
The preamble to the announcements was somewhat predictable if not old. Sustainability Goals, Companies moving Critical Workloads (NASDAQ) to the Cloud. Re-iterated all the benefits of cloud, Velocity, Agility, Elasticity, Cost (who hasn't heard this by now?).

There was a great slide that sums up all of the above. The cloud allows you to "Be Prepared for Anything". Cyber-Monday? No problem, scale up. Pandemic and no one is needing your service? Scale down, or off. Need to try something new? Get up and running quickly. Need to Pivot? Shut off that service.

OK, onto the announcments!

## Announcement 1 - OpenSearch Serverless [>](https://aws.amazon.com/blogs/aws/preview-amazon-opensearch-serverless-run-search-and-analytics-workloads-without-managing-clusters/)

Run large-scale search and analytics workloads without managing clusters. Pay only for the data that is ingested and the queries you run. 
![Open Search Serverless](assets/images/aws/opensearch.png)

**Takeaway:** AWS now has a complete "Serverless" offering for its analytics services. OpenSearch is AWS's implementation of ElasticSearch. This allows teams to get up and running quickly with minimal cost, allowing for rapid solution prototyping a variety of use cases for a number of use cases such as log analytics, application search, enterprise search, and more.

## Theme AWS zero-ETL Vision

Adam announced AWS zero-ETL vision. Traditional data engineering requires multiple data pipelines to get data from transactional / operational databases to data warehouses (Redshift). These all need to be tested, and changed according to business needs (lots of work). The zero-ETL vision seeks to eliminate the need for this in the future. The next two announcements contribute to this vision.

## Announcement 2 - Aurora zero-ETL integration with Redshift [>](https://aws.amazon.com/about-aws/whats-new/2022/11/amazon-aurora-zero-etl-integration-redshift/)

Enable near real-time analytics and machine learning (ML) using Amazon Redshift on petabytes of transactional data from Aurora. Within seconds of transactional data being written into Aurora, the data is available in Amazon Redshift, so you don’t have to build and maintain complex data pipelines to perform extract, transform, and load (ETL) operations.

![Aurora zero-ETL integration with Redshift](assets/images/aws/aurorazeroetl.png)

**Takeaway:** This is initially only supported on Aurora MySQL3 databases and is currently in Preview. IMO it eliminates E (extract) and L (load), because the way I currently understand it, transactional data is written as in Aurora (no T - Transformation) of data takes place. This does solve the problem of having users query/perform analytics on Operational Databases, by shuffling the data to Redshift, thereby reducing impact to Operational Processes.

## Announcement 3 - Redshift integration for Apache Spark [>](https://aws.amazon.com/blogs/aws/new-amazon-redshift-integration-with-apache-spark/)
Builds upon an existing open-source connector project and enhances it for performance and security, helping customers gain up to 10x faster application performance.

![Redshift integration for Apache Spark](assets/images/aws/sparkredshift.png)

**Takeaway:** This was an existing capability via an Open Source Project started by Databricks and maintained by the community. Amazon worked with the community to improve the performance and security, elevating it to a fully supported feature. (so existing capability that is not officially supported).

## Announcement 4 - Datazone (New Service!) [>](https://aws.amazon.com/datazone/)
Data Governance - a data management service that you can use to publish data and make it available to the business data catalog through your personalized web application. You can access your data more securely regardless of where it is stored.

![Redshift integration for Apache Spark](assets/images/aws/datazone.png)

**Takeaway:** Governance? People don't want to hear about governance, but they can get behind data discovery, data quality, data access, and data security. Get with your Data Analysts, and they will tell you "just give me access". Well, with the newly announced Amazon Datazone, you can stop talking about governance, and instead improve the usability of data for your analysts (and govern your data). AWS was lacking this capability. Azure had "Data Catalog", which was "rebooted" into Azure Purview. This is an enterprise need. Lot's of integration with AWS data products.

## Announcement 5 - Security Lake [>](https://aws.amazon.com/blogs/aws/preview-amazon-security-lake-a-purpose-built-customer-owned-data-lake-service/)
Automatically centralizes your organization’s security data from cloud and on-premises sources into a purpose-built data lake stored in your account.

![Security Lake](assets/images/aws/securitylake.png)

**Takeaway:** Provides alternatives to SIEM (Security Incident and Event Management) products (eg Splunk), and provides integrations with existing AWS Services. Benefit of a common schema for logging (OCSF) Open Cybersecurity Schema Framework, for potential interoperability with 3rd party services.

## Announcement 6 - More Compute Instances
Building upon advancements highlighted in Peter DeSantis' keynote yesterday, multiple new EC2 compute instances were announced, from [standard](https://aws.amazon.com/blogs/aws/new-general-purpose-compute-optimized-and-memory-optimized-amazon-ec2-instances-with-higher-packet-processing-performance/) workloads, [network and HPC intensive](https://aws.amazon.com/blogs/aws/new-amazon-ec2-instance-types-in-the-works-c7gn-r7iz-and-hpc7g/) workloads, and [Deep Learning](https://aws.amazon.com/about-aws/whats-new/2022/11/aws-announces-amazon-ec2-inf2-instances-preview/) workloads.

![Compute](assets/images/aws/computeinstances.png)

**Takeaway:** This is an AWS core competency, as we saw from last nights keynote, the engineering happening at the datacenter and silicon level is paying dividends at the compute level. Some of these machines are very highly specialized for large workloads (life sciences, industrial engineering, etc), not something a lot of enterprises use.

## Announcement 7 - SimSpace Weaver [>](https://aws.amazon.com/blogs/aws/new-aws-simspace-weaver-build-large-scale-spatial-simulations-in-the-cloud/)
A new compute service to run real-time spatial simulations in the cloud and at scale. SimSpace Weaver is great at simulating crowds. This is very useful, for example, when you’re planning large events or planning to build infrastructure like a new stadium. It is also ideal for simulating smart cities, complete with vehicles, inhabitants, and other objects.

![SimSpace Weaver](assets/images/aws/simspace.png)

**Takeaway:** Highly specialized service. If you are running these types of workloads today, you will be really happy to see this, if not..ho hum.

## Announcement 8 - Connect Capabilities [>](https://docs.aws.amazon.com/connect/latest/adminguide/amazon-connect-release-notes.html#nov22-release-notes)
  * Create step-by-step guides for your agents
  * ML Driven forecasting, capacity planning, and scheduling
  * Contact Lens Enhancements

![Connect](assets/images/aws/connect.png)

**Takeaway:** New features added. In the future AWS should break these BizApps out to a separate conference, especially as they continue to grow their portfolio (see SupplyChain announcement)

## Announcement 9 - Clean Rooms (New Service!) [>](https://aws.amazon.com/clean-rooms/)
Helps customers and their partners to more easily and securely match, analyze, and collaborate on their combined datasets–without sharing or revealing underlying data.

![Clean Rooms](assets/images/aws/cleanrooms.png)

**Takeaway:** Allows data sharing while protecting data. Excited about this! 
In the past, it was a challenge to setup data pipelines and integrations just to share data. 
I always argued that we could spend that time getting more of our data centralized to a data lake, then share that data through controls. Clean Rooms solves this problem. Azure has this capability, but (Azure Data Sharing, I believe, but doesn't look as robust as this)

## Announcement 10 - Supply Chain [>](https://aws.amazon.com/aws-supply-chain/)
Supply Chain can connect to your existing enterprise resource planning (ERP) and supply chain management systems, without requiring replatforming, upfront licensing fees, or long-term commitments.

![Supply Chain](assets/images/aws/supplychain.png)

**Takeway:** AWS moving further into Business Apps. Is this an opening shot to established ERP vendors? Not an area I am very familiar with. Is AWS going after the Oracle and SAPs of the world? Again, not fitting the profile of the majority of attendees, but a whole new area.

## Announcement 11 - Omics [>](https://aws.amazon.com/aws-supply-chain/)
Helps healthcare and life science organizations store, query, and analyze genomic, transcriptomic, and other omics data and then generate insights from that data to improve health and advance scientific discoveries.

![Omics](assets/images/aws/omics.png)

**Takeway:** If you are in the Life Sciences or Healthcare industry, you may be excited. I am not.

## In Closing
I'm working on centralizing this by area and product. Here's an example of what I've done so far. I will publish the final list at the end of the conference.

## Let's Connect
If you are attending AWS re:Invent or noticed a session that I might have missed, you can reach out to me on:
  1. Mastodon - [@mikelor@awscommunity.social](https://awscommunity.social/@mikelor)
  1. GitHub - [@mikelor](https://github.com/mikelor)
  1. LinkedIn - [mlorengo](https://www.linkedin.com/in/mlorengo/)
  1. Twitter - [@mikelor](https://twitter.com/mikelor)
