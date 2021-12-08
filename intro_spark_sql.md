
## Introduction to Apache Spark and SparkSQL using Databricks Community Edition


When we start discussing big data, we often find ourselves talking about the five v's of big data. Those v's are **volume**, **velocity**, **variety**, **veracity** and **value**.
<br>
- **Volume**: consider the massive amounts of data that's being generated every second of every day.

- **Velocity**: the frequency at which new data is generated and the speed at which it moves around.

- **Variety**: relates to the different types and the different sources of data. 

- **Veracity**: refers to the quality an accuracy of data.

- **Value**: actionable insights which can be made visible to a wider audience



Often Data Scientists suffer from a lack of proper tools that will work with various data sources with multiple file formats. For instance, some data storage solutions may have multiple different databases, a solution could be more centralised like a data wareshoure or one solution could be a data lake which can store unstructured, semi-structured and structured data altogether allowing a unified team work on a single source of truth.

However, in order to enable big data workloads to work in systems like these, the most appropriate tool for the task should be chosen. For Data Scientists, it is important to have a tool which can scale beyond spreadsheet workflows and that can handle working with multiple data sources, such as a mixture of csv/excel, BI platforms, DBMS or SQL, etc.



### 1. Spark

![Apache Spark](images/apache_spark_logo_icon_170561.png)

Apache spark is an analytics engine designed to unify data teams and meet big data needs. Among the big data community, it is very well known and widely used for its speed is abuse in generality. That is its ability to seamlessly integrate data. Applications that can include SQL streaming or complex analytics.

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






