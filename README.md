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
<p><ul>
         <li>Provides support for in-memory data processing; it can access or analyze data stored on Hadoop Datanodes without any data movement. </li>
         <li>Using Impala, we can access data using SQL like queries. </li>
         <li>Apache Impala provides faster data access to data stored in Hadoop Distributed File System compated to other SQL engines like Hive. </li>
         <li>Impala helps us store data in Storage systems like Hadoop Hbase, HDFS and Amazon s3.</li>
         <li>We can easily integrate Impala with business intelligence tools such as Tableau, Micro strategy, P Pentaho and Zoom Data. </li>
         <li>Provides support for various file formats such as LZO, Avro, RCfile, Sequence file and Parquet. </li>
         <li>Apache impala uses the ODBC driver, user interface metadata, and SQL syntax such as Apache Hive. </li>
     </ul></p>
     
 <h3><b>Conclusion.</b></h3>
 <p>In short, we can say that Impala is an open-source and native analytics database for Hadoop. Impala is the most powerful SQL engine that provides the fastest access to data stored in HDFS (Hadoop Distributed File System).
Impala uses the same Hive Query Language (SQL) syntax, metadata, user interface, and ODBC drivers as Apache Hive. Unlike traditional storage systems, Apache impala is not tied to its storage core. It consists of three core components Impala daemon, Impala state store, and Impala Catalog. The Impala Shell, the Hue browser, and the JDBC/ODBC driver are three query processing interfaces we can use to interact with Apache Impala.</p>


