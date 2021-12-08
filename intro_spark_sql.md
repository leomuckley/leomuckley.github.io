
## Introduction to Apache Spark and SparkSQL

**Overview:** 
Python implementation of the paper title *Approximating Mutual Information by Maximum Likelihood Density Ratio Estimation* [].
<br><br>


When we start talking about big data, you'll find that it's often characterized by what people call the five v's of big data. Those v's are volume, velocity, variety, veracity and value.

When we talk about volume, we're talking about the massive amounts of data that's being generated every second of every day.

When we refer to velocity, we're referring to the speed at which new data is generated and the speed at which data moves around.

The next v is variety, and it refers to having different types and sources of data. 

The next v, we want to talk about is veracity, which refers to the quality an accuracy of data.

Scalability - working with spreadhseets, long processing time

Working with multiple data sources - mixture of csv/excel, BI platforms, DBMS or SQL, etc.

Extracting value from big data can be really complicated and it needs to be transformed into shareable, actionable insights and made visible to the larger organization.


Definitely, data analyst sometimes suffer from a lack of proper tools, or working with multiple data sources in a disconnected system. And finding that maybe there isn't a single source of truth for the company. So what can we do to make these struggles better? Data teams need a well-designed data infrastructure so that it's clear where they can go to access information. Universal tools that work with multiple different file formats and with different file sources. A single source of truth that they can trust for reliable information. And to work on a unified data team, where we're sure that all of the parts of the team are working with the same data.


Some data storage solutions might look like multiple different databases, for a particular business needs. For example, you might have one that is designated to sales data, and then another for operations data, and then finance data is stored in a database separate from those. Another choice might be a centralized data repository like a data warehouse. That's a little bit like the previous system, except it goes and brings all of those multiple different databases under one roof, so you're still working in a single system, but you still have all that same structure where everything is very much separated out. Then, recently, data lakes have become really popular for storage.
But I'll say now that data lakes are popular because they can store unstructured and semi-structured and structured data altogether, and it gives that single source of truth that we've been talking about.

In order to enable big data workloads, we'll need to choose tools that are designed to work in a system like this.


### 1. Spark

So what is Apache Spark? Apache spark is an analytics engine designed to unify data teams and meet big data needs. Among the big data community, it is very well known and widely used for its speed is abuse in generality. That is its ability to seamlessly integrate data. Applications that can include SQL streaming or complex analytics.

In a distributed computing edge and what's going to happen is you're going to feed in the workload. And then that work is going to be distributed across a cluster of machines. This means that you can distribute that large workload among a few different machines. An all of them can be working on the problem simultaneously.

Another benefit to working with spark is that you can connect to multiple data stores in the eye tools. So in terms of where we're going to get data from, we can start off using Spark. And from there we can pull in data from just regular cloud storage or we can pull in data from a traditional SQL database. Or we can pull in data from a data lake or in what we have here is a Delta Lake which will talk about later. 




### 2. SparkSQL


Spark SQL is built to work with Spark an is designed for structured data processing. It allows us to use basic SQL syntax to access Spark's unified analytics engine.

So why use Spark SQL? Well, ease of use for one, it makes it really easy for SQL users to work with Spark. You can run exactly the same queries and commands you're used to, plus access some additional functionality all using a standard SQL syntax.

Beyond that, we'll also see the benefits of Spark's super cool optimization engine. Each query you run is going to be passed through an optimization engine that is designed to give you the best possible performance. So it can adjust the order of the business logic you express or it can skip reading unnecessary data, and you can find the most cost efficient way to deliver your results.

#### DataBricks

First, we're going to get you signed up on Databricks Community Edition so you can start using Spark, power your queries. Databricks Community Edition is a free version of the Databricks platform. As I mentioned earlier, all of us work for Databricks, which is a unified platform for massive scale data engineering, collaborative data science, full cycle machine learning and business analytics.

#### Workspace

A cluster is the set of computational resources that will power your queries. All work on Databricks must be powered by a cluster. To do this, simply click on the Clusters tab in the sidebar, and then click ''New Cluster''. 

#### Create a quickstart cluster

1. In the sidebar, right-click the **Compute** button and open the link in a new window.
1. On the Clusters page, click **Create Cluster**.
1. Name the cluster **Quickstart**.
1. In the Databricks Runtime Version drop-down, select **7.3 LTS (Scala 2.12, Spark 3.0.1)**.
1. Click **Create Cluster**.






