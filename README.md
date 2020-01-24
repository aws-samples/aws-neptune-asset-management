## Connected Platform – Integrating Sales and Service with AWS Neptune

Deciphering and exploring relationships that exists between sales and service can help companies drive revenue.   AWS Neptune can help companies realize and explore trends, make better recommendations, and easily navigate highly connected and complex datasets.  Amazon Neptune is a fast, reliable, fully managed graph database service that makes it easy to build and run applications.  Neptune can serve as an asset management platform, connecting sales and service data across the organization.

In this workshop, we will build a connected graph that integrates sales and service data using AWS Neptune.  Once the graph is built, we will explore how sales analysts can use sale and service data in Neptune to identify additional sales opportunities.

## Architecture

The high-level graph for this workshop is the following:

![Architecture](/images/architecture.jpg)

## Connected Platform – Sales and Service

The graph above is constructed based on the following fictitious scenario:

John (dark blue ellipse) is a scientist and an employee of ACME lab corporation (light blue ellipse).  John has purchased an Ultra-Low Temperature (ULT) freezer, DNA Sequencer (QuantStudio), and a master mix regent to perform his experiments.  As John works with these instruments, his freezer door malfunctions.  ACME corporation has a ‘silver’ tier contract and notifies the manufacturer that the freezer door has malfunctioned.  The manufacturer of the freezer assigns a service ticket to a knowledgeable service technician, Joe (orange ellipse).  


### Building the knowledge graph.
This workshop constructs and builds relationship between sales and service data in AWS Neptune.  Typically, sales and service data exist in desperate and siloed systems, but AWS Neptune can be used as a central asset management platform, connecting sales and service data. As data flows through the corporate systems, Neptune APIs can be used to store and build relationships between entities.  In this workshop, you will insert sales and service data using Neptune workbench. Once the graph is built, an analyst can run queries to drive revenue for the business. 

In order to build the above knowledge graph, you will launch a Neptune cluster and execute the provided notebook.

<b>Launch Neptune Cluster</b>
</br>
In this section, you will learn how to launch a fully managed Neptune cluster.

<b>Prerequisites:</b>
1.	Sign-in to AWS or [Create an Account](https://us-west-2.console.aws.amazon.com/)

<b>Creating a Neptune Database</b>
</br>
1.	Go to [Neptune Console](https://console.aws.amazon.com/neptune/home?)
2. Click <b>Launch Amazon Neptune </b> or <b>Create Database </b>
3.	Enter the following specifications </br>
  a.	DB Engine: 1.0.2.1.R4 </br>
  b.	DB instance size: db.r4.large </br>
  c.	Enable High Availability – No </br>
  d.	Instance identifier: <your_initials_neptune_db>

4. Click <b>Next</b>
 
![database specification](/images/create_instance.png)

1.	Leave network & security to <b>default</b> configuration
2.	Under DB options, enter DB cluster identifier <b> <your_initials_neptune_cluster> </b>
3.	Leave all other fields as default
4.	Click <b> Create database </b>
5. It will take a few minutes for database status to become <b>available </b>
  
### Launch Neptune Workbench
In this section, you will learn how to launch the Neptune workbench and run gremlin queries.

1.	Go to [Neptune Console](https://console.aws.amazon.com/neptune/home?)
2.	Form the left navigation pane, select <b>Notebooks</b>
3.	Click <b>Create notebook</b>

![Creating a notebook](/images/creating_notebook.png)

4.	Under Notebook Configuration, enter the following:</br>
a.	Choose previously created cluster <b> <your_initials_neptune_cluster> </b> </br>
b. Enter Notebook name <b> <asset-management-notebook> </b> </br>
c.	Select <b>Create IAM Role </b> </br>
d.	Enter IAM role name <b><your-initials-neptune-notebook-role> </b> </br>
e.	Click <b>Create notebook </b>

![notebook configuration](/images/notebook_configuration.png)

5.	Once the neptune notebook status is <b>Ready </b>, click on select notebook and click <b>Open notebook</b>
6.	Click <b>Neptune </b> directory
7.	Click <b>upload</b>
8.	Upload the provided Neptune notebook <b> < assetmanagement.ipynb> </b>
9.	Open the Jypiter notebook, read the instructions, and execute each cell to build the asset management graph.
10.	Follow the instructions on the Jypiter notebook to complete the lab.



## License

This library is licensed under the MIT-0 License. See the LICENSE file.

