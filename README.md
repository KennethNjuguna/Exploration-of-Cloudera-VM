<h2> Training exercises for Cloudera's Distribution for Hadoop; Cloudera is a Hybrid Data company. </h2>

-------------------------------------------------------------------------------------------------------

<p>Cloudera's distribution for Hadoop provides a number of services</p> 
<p> This includes:- </p>
<ul>
         <li>HBase</li>
         <li>Hue</li>
         <li>Impala</li>
         <li>Oozie</li>
         <li>Spark</li>
      </ul>
      
-------------------------------------------------------------------------------------------------------- 
<p><h3><li>HBase</li></h3></p>

<p><li>Workflow scheduler system to manage Apache Hadoop jobs.</li></p>
<p><li>Oozie Coordinator jobs.</li></p>
<p><li>Supports: MapReduce, Pig, Apache Hive, and Sqoop .</li></p>
<p>Workflows in Oozie are defined as a collection of control flow and action nodes in a directed acyclic graph. Control flow nodes define the beginning and the end of a workflow (start, end, and failure nodes) as well as mechanism to control the workflow execution path(decision fork and jon nodes).</p>

--------------------------------------------------------------------------------------------------------

<p><h3><li>Hue (Hadoop User Experience)</li></h3></p>
<p> Hue is a web-based interactive query editor that enables you to interact with data warehouses. For example, the following image shows a graphic representation of Impala SQL query results that you can generate with Hue. </p>

![image](https://user-images.githubusercontent.com/97665556/216337193-b285a3c3-2703-4e1a-b14d-988fd4b948c7.png)
<p> You can use Hue to:- </p>
<p><li><b>Explore, browse and import your data </b> through guided navigation in the left panel of the page: </li></p>

![image](https://user-images.githubusercontent.com/97665556/216339073-83dd625a-b69c-46e9-af88-1bd4db8a7f97.png)

<p>This panel enables you to: </p>
<ul>
         <li>Browse your databases</li>
         <li>Drill down to specific tables</li>
         <li>View HDFS directories and Cloud storage</li>
         <li>Discover indexes and HDFS or kudu tables</li>
         <li>Find documents</li>
 </ul>
 
 <p>Objects can be tagged for quick retrieval, project association, or to assign a more "human readable" name if desired. </p>
 <p><b><ol><li>Query your data, create a custom dashboard or schedule repetitive jobs</li></ol></b> in the central panel of the page. </p>
 
 ![image](https://user-images.githubusercontent.com/97665556/216589222-22ee4f15-d084-4503-8699-95222a4106f3.png)

<p> The central panel of the page provides a rich toolset, including:- </p>
<p><ul><li><b>Versatile editors </b>that enable you to create a wide variety of scripts. </li>
         <li><b>Dashboards </b>that you can create "0n-the-fly" by dragging and dropping elements into the central panel of the Hue interface. No programming is required. Then you can use your custom dashboard to explore your data. </li>
         <li><b>Schedulers </b>that you can create by dragging and dropping, just like the dashboards feature. This feature enables you to create custom workflows and to schedule them to run automatically on a regular basis. A monitoring interface shows the progress, logd, and makes it possible to stop or pause jobs. </li>
         </p>
         
         
<p><li><b>Get expert advice on how to complete a task: </b></li></p>
         
![image](https://user-images.githubusercontent.com/97665556/216936755-53522b4a-72a5-454a-ab27-42e6eb99171b.png) 

         
<p>The assistant panel on the right provides expert advice and hints for whatever application is currently being used in the central panel. For example, in the above image, Impala SQL hints are provided to help construct queries in the central panel. </p>

<p><h3><li>Impala</li></h3></p>
<p> Impala provides fast, interactive SQL queries directly on your Apache Hadoop data stored in HDFS, HBase, or Amazon Simple Storage Service (S3). In addition to using the same unified storage platform, Impala also uses the same metadata, SQL syntax (Hive SQL), ODBC driver, and user interface (Impala query UI in Hue) as Apache Hive. This provides a familiar and unified platform for real-time or batch-oriented queries. </p>

<p>Impala is an addition to tools available for querying big data. Impala does not replace the batch processing frameworks built on MapReduce such as Hive. Hive and other frameworks built on MapRedcue are best suited for long running batch jobs, such as those involving batch processing of Extract, Transform, and Load (ETL) type jobs.</p>

<p><h4><b>How Impala works with Apache Hadoop</b></h4></p>
<p>The Impala solution is composed of the following components:</p>
<p><li>Clients - Entities including Hue, ODBC clients, JDBC clients, and the Impala Shell can all interact with Impala. These interfaces are typically used to issue queries or complete administrative tasks such as connecting to Impala. </li></p>

<p><li>Hive Metastore - Stores information about the data available to Impala. For example, the metastore lets Impala know what databases are available and what the structure of those databases is. As you create, drop, and alter schema objects, load data into tables, and so on through Impala SQL statements, the relevant metadata changes are automatically broadcast to all Impala nodes by the dedicated catalog service introduced in Impala 1.2. </li></p>

<p><li>Impala - This process, which runs on DataNodes, coordinates and executes queries. Each instance of Impala can receive, plan, and coordinate queries from Impala clients. Queries are distributed among Impala nodes, and these nodes then act as workers, executing parallel query fragments. </li></p>


<p><li>HBase and HDFS - Storage for data to be queried. </li></p>

<p>Queries executed using Impala are handled as follows:</p>
<p><li>User applications send SQL queries to Impala through ODBC or JDBC, which provide standardized querying interfaces. The user application may connect to any impalad in the cluster. This impalad becomes the coordinator for the query. </li></p>

<p><li>Impala parses the query and analyzes it to determine what tasks need to be performed by impalad instances across the cluster. Execution is planned for optimal efficiency. </li></p>

<p><li>Services such as HDFS and HBase are accessed by local impalad instances to provide data.. </li></p>

<p><li>Each impalad returns data to the coordinating impalad, which sends these results to the client.</li></p>

<h3><b>Primary Impala Features.</b></h3>
<p> The key features of Impala are:- </p>
<ul>
         <li>Provides support for in-memory data processing; it can access or analyze data stored on Hadoop Datanodes without any data movement. </li>
         <li>Using Impala, we can access data using SQL like queries. </li>
         <li>Apache Impala provides faster data access to data stored in Hadoop Distributed File System compated to other SQL engines like Hive. </li>
         <li>Impala helps us store data in Storage systems like Hadoop Hbase, HDFS and Amazon s3.</li>
         <li>We can easily integrate Impala with business intelligence tools such as Tableau, Micro strategy, P Pentaho and Zoom Data. </li>
         <li>Provides support for various file formats such as LZO, Avro, RCfile, Sequence file and Parquet. </li>
         <li>Apache impala uses the ODBC driver, user interface metadata, and SQL syntax such as Apache Hive. </li>
     </ul>
     
 <h3><b>Conclusion.</b></h3>
 <p>In short, we can say that Impala is an open-source and native analytics database for Hadoop. Impala is the most powerful SQL engine that provides the fastest access to data stored in HDFS (Hadoop Distributed File System).
Impala uses the same Hive Query Language (SQL) syntax, metadata, user interface, and ODBC drivers as Apache Hive. Unlike traditional storage systems, Apache impala is not tied to its storage core. It consists of three core components Impala daemon, Impala state store, and Impala Catalog. The Impala Shell, the Hue browser, and the JDBC/ODBC driver are three query processing interfaces we can use to interact with Apache Impala.</p>

<p><h3><li>Oozie</li></h3></p>
<p> The blueprint for Enterprise Hadoop includes Apache™ Hadoop’s original data storage and data processing layers and also adds components for services that enterprises must have in a modern data architecture: data integration and governance, security and operations. Apache Oozie provides some of the operational services for a Hadoop cluster, specifically around job scheduling within the cluster. </p>

<p><h2>What Oozie Does </h2></p>
<p>Apache Oozie is a Java Web application used to schedule Apache Hadoop jobs. Oozie combines multiple jobs sequentially into one logical unit of work. It is integrated with the Hadoop stack, with YARN as its architectural center, and supports Hadoop jobs for Apache MapReduce, Apache Pig, Apache Hive, and Apache Sqoop. Oozie can also schedule jobs specific to a system, like Java programs or shell scripts.

Apache Oozie is a tool for Hadoop operations that allows cluster administrators to build complex data transformations out of multiple component tasks. This provides greater control over jobs and also makes it easier to repeat those jobs at predetermined intervals. At its core, Oozie helps administrators derive more value from Hadoop. </p>

<p>It consists of two parts:- </p>
<p><ul>
         <li><b>Workflow engine:</b> Responsibilty of a workflow engine is to store and run workflows composed of hadoop jobs e.g Mapreduce, Oozie and Hive.</li>
         <li><b>Coordinator Engine: </b> It runs workflow jobs based on predefined schedules and availability of data. </li></p>
<p>OOzie is scalable and can manage the timely execution of thousands of workflows each consisting of dozens of jobs in a Hadoop cluster.</p>

![image](https://user-images.githubusercontent.com/97665556/219648434-e74c196a-e16f-4f2c-9c5a-7e61366a137e.png)


<p>Oozie is very much flexible, as well. One can easily start, stop, suspend and rerun jobs. Oozie makes it very easy to rerun failed workflows. One can easily understand how difficult it can be to catch up missed or failed jobs due to downtime or failure. It is even possible to skip a specific failed node. </p>

<p><h2><b>How does Oozie work.</b> </h2></p>
<p><ul>
         <li>Oozie runs as a service in the cluster and clients submit workflow definitions for immediate or later processing.</li>
         <li>Oozie workflow consists of <b>action nodes</b> and <b>control-flow nodes.</b></li>
         <li>An <b>action node</b> represents a workflow task, e.g., moving files into HDFS, running a MapReduce, Pig or Hive jobs, importing data using Sqoop or                   running a shell script of a program written in Java.</li>
         <li>A <b>control-flow node</b> controls the workflow execution between actions by allowing constructs like conditional logic wherein different branches may be                    followed depending on the result of earlier action node.</li>
         <li><b><b>Start Node</b>, End Node, and Error Node</b> fall under this category of nodes.</li>
         <li><b>Start Node</b>, designates the start of the workflow job.</li>
         <li><b>End Node</b>, signals end of the job.</li>
         <li><b>Error Node</b> designates the occurrence of an error and corresponding error message to be printed.</li>
         <li>At the end of execution of a workflow, HTTP callback is used by Oozie to update the client with the workflow status. Entry-to or exit from an <b>action                   node </b>may also trigger the callback. </li>
         
 <p><h3><li>Spark.</li></h3></p>
 <p><b>Apache Spark </b> is the open standard for flexible in-memory data processing that enables batch, real-time, and advanced analytics on the Apache Hadoop platform. Cloudera is committed to helping the ecosystem adopt Spark as the default data execution engine for analytic workloads.</p>
 
 <p><h2>Easy, Productive Development.</h2></p>
<p>Simple, yet rich, APIs for Java, Scala, and Python open up data for interactive discovery and iterative development of applications. Through shared common code, data scientists and developers can increase productivity with rapid prototyping for batch and streaming applications, using the language and third-party tools on which they already rely. </p>

<p><h2>Fast Processing.</h2></p>
<p>Take advantage of Spark’s distributed in-memory storage for high performance processing across a variety of use cases, including batch processing, real-time streaming, and advanced modeling and analytics. With significant performance improvements over MapReduce, Spark is the tool of choice for data scientists and analysts to turn their data into real results.</p>

<p><h2>Integrated across the platform.</h2></p>
<p>As an integrated part of Cloudera’s platform, Spark benefits from unified resource management (through YARN), simple administration (through Cloudera Manager), and compliance-ready security and governance (through Apache Sentry and Cloudera Navigator) — all critical for running in production.</p>

<p><h2>The Cloudera difference for Apache Spark.</h2></p>
<p>The first integrated solution to support Apache Spark, Cloudera not only has the most experience — with production customers across industries — but also has built the deepest engineering integration between Spark and the rest of the ecosystem, including bringing Spark to YARN and adding necessary security and management integrations (500+ patches contributed, to date). Cloudera also has multiple Spark committers on staff, so you get direct access and influence to the roadmap based on your needs and use cases.</p>

<p><h2>Features of Apache Spark.</h2></p>
<p><h3><li>Batch/streaming data.</li></h3></p>
<p>Unify the processing of your data in batches and real-time streaming, using your preferred language: Python, SQL, Scala, Java or R.</p>

<p><h3><li>SQL Analytics.</li></h3></p>
<p>Execute fast, distributed ANSI SQL queries for dashboarding and ad-hoc reporting. Runs faster than most data warehouses.</p>

<p><h3><li>Data Science at a Scale.</li></h3></p>
<p>Perform Exploratory Data Analysis (EDA) on petabyte-scale data without having to resort to downsampling.</p>

<p><h3><li>Machine learning.</li></h3></p>
<p>Train machine learning algorithms on a laptop and use the same code to scale to fault-tolerant clusters of thousands of machines.</p>

<p><h2>Differences between Apache spark and Hadoop </h2></p>

<p>Spark and Hadoop are leading open source big data infrastructure frameworks that are used to store and process large data sets. </p>

<p>Since Spark's introduction to the Apache Software Foundation in 2014, it has received massive interest from developers, enterprise software providers, and independent software vendors looking to capitalize on its in-memory processing speed and cohesive, uniform APIs. </p>

<p>However, there is a hot debate on whether Spark can replace Hadoop to become the top big data analystics tool.</p>

<p>In this post, I have tried to explain the difference between Spark and Hadoop easily so that anyone, even those without a background in computer science, can understand.</p>

<p><h3>Distributed Storage System.</h3></p>
<p>Even though Spark is said to work faster than Hadoop in certain circumstances, it doesn't have its own distributed storage system. So first, let's understand the concept of a distributed file system. </p>

<p>Distributed storage system lets you store large datasets across an infinite number of servers, rather than storing all the datasets on a single server. </p>

<p>When the number of data increases, you can add as many servers as you want in the distributed storage system. This makes a distributed storage system scalable and cost-efficient because you are using additional hardware (servers) only when there is a demand. </p>

<p><h3>How Spark and Hadoop Process Data.</h3></p>
<p>Spark does not have its system to organize files in a distributed way(the file system). For this reason, programmers install Spark on top of Hadoop so that Spark’s advanced analytics applications can make use of the data stored using the Hadoop Distributed File System(HDFS). Hadoop has a file system that is much like the one on your desktop computer, but it allows us to distribute files across many machines. HDFS organizes information into a consistent set of file blocks and storage blocks for each node. </p>

![image](https://user-images.githubusercontent.com/97665556/224050020-859f3804-aa9f-478e-bea0-fd74f0b4099a.png)

<p> HDFS uses MapReduce to process and analyze data. MapReduce takes the back of all the data in a physical server after each operation. This was done because data stored in a RAM is volatile than that stored in a physical server. </p>

![image](https://user-images.githubusercontent.com/97665556/224050168-aaa499a8-5a1d-4d97-9b01-5dbd3fa5b931.png)

<p> In contrast, Spark copies most of the data from a physical server to RAM; this is called “in-memory” operation. It reduces the time required to interact with servers and makes Spark faster than the Hadoop’s MapReduce system. Spark uses a system called Resilient Distributed Datasets to recover data when there is a failure. </p>




         
         



