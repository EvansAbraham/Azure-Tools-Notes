## Azure Data Factory Deployment

### Purpose
&nbsp; It isused to refine and process the dataset and increase it's value

### Steps to proceed
- Create a Resource in order to do that go to resource place and search for Data Factory (or) Factory.
- Make sure to have a subscriptiona and create a resource group in order to store the resource files of the data factory.
- Create an instance name which should be globally unique.
- Select the region.
- Review and create as the other options are not necessary for the begineers in the initial.
- Deploy the instance and wait for it's deployment

### Instance in ADF
- Name of the instance can't be changed once it is give or created but it can be moved from one resource group to another resource group or from one subscription to another subscription.
- Activity Log is used to log down all the write operation that is done in that particular ADF instance but not the read operations only the write operation.
- Next the access control panel for configuring the role-base access control for min role configuration or least role configuration.
- Each roles work across every other platforms in Azure but there are specific roles that are ment for the ADF such as Data Factory Contributer.
- Tagging functionality is similar to normal tagging.
- Next one is the Diagnosis button which is very helpful in the time of our troubleshooting.
- Next is the networking configuration instance which we already seen in the deployment plate.
- Managed Identity configuration which is set on by default and that means that we have an object principle ID within our active directory tenant that can be used for assigning roles for particular instances for a step called Zero Trust Security Configuration.
- Locks - it is used to protect the DF from being deleted or changed accidentally.

### Functionalities of the ADF UI
- At first it has some ingesting the data functionality.
- Next is the Orchestrate to create code-free data piplining.
- Next is Transform Data that is used to transform the data using the Data Flows.
- Data Factory is a similar product that is developed previously by Microsoft itself called SQL Server Integration Services (SSIS).
---
## ADF Basic Object Model
### Types of Object Model
&nbsp;There are four basic object model in ADF. They are 
- Data Set
- Linked Service
- Activity
- Pipeline
### Uploading the Datasets
- In order to upload a dataset we need to create a storage account.
- Next we need to create a storage container in order to store the necessary files for our data factory.
- Link the container to respective resource manager

### Configuring the sample data
- Start by clicking ingest and the choose at what duration the process should work.
- Choose the source type such as either it is a cloud based or on premises in order to create a dataset.
- Next choose the connection of the database that you need to access in order to create a dataset.
- Then create the source for the dataset for the datafactory.
- Next choose the destination for the dataset in the datafactory.
- Verify the settings such as task name and description and proceed to the review section.
- After reviewing the datasets proceed to finish and deploy the datasets.

### Data copy pipeline results
- Pipeline is a orchestrated procedure with atleast one action
### Review object model and clean-up
- Inorder to delete the linked service the related dataset and pipeline should be deleted and it should be published in order to delete the linked service.
---
## Data Transformation
### Data Flow
- Ways to create a data flow
	- Clicking new in the home page and selecting the Data Flow
	- Clicking the author section and go to data flow and create a new data flow
	- In the home page click the transform data option.
- Next create one or more data source based on our requirements
	- Under that data source specify the dataset that you're going to use in the data flow of the data factory.

### Filtering the Data
- Click the + icon near the data source in order to perform the respective action for the data source and for filter scroll below and click the filter option.
- Next we need to set attributes for filtering the data so by clicking the expression builder we can create the expressions for filtering the data.
- Make sure to enable debug mode to preview our works.
- After adding the filter or anyother operation that is required for the dataset next the destination is choosen such as **Sink**.
- Select the destination file for the filtered data to be stored.
- Next Validate the dataflow inorder to check for any errors and mistakes.
---
## Orchestration
### Creating an Orchestrate
- Once the data flow is created the data flow cannot be orchestrated itself instead we need to create an orchestra to orchestrate the data set
- By clicking the orchestrate button it will directly redirect to the pipelining option creating a new pipeline.
- Below the move and transform option we can find Data flow option. Drag & Drop it in the canvas.
- Go to the settings option and click settings and choose the data flow that is need to be procesed.
- Next click validate the orchestra and the publish in order to trigger the data flow.
---
## ADF Advance Object Model
### Triggers
- Click the pipeline that is required to have trigger and click the pipeline and then click the trigger option that is on the above panel.
- Name your trigger and then choose its type. There are four type of triggers. They are 
	- Schedule
	- Tumbling Window
	- Storage Events
	- Custom Events
#### Schedule 
- The Schedule type  trigger is selfexplaining one such that it will trigger when the time is set and at that time it will directly start to trigger.
#### Tumbling Window
- It is similar to Schedule but the recurrance timing is not set below 5 mins
- It also gives us the extra options of specifying the dependencies between the triggers
#### Storage Event
- In this the trigger is not based on the time based trigger but an actual event that is occured in the storage account such as a new blob is added etc.
#### Custom Event
- It is related to an Azure service called Azure Event Grid.
- So if an Instance is created on the Azure Event Grid on our Azure Subscription, it can also listen to the the event such that listening to the IoT Hub, Azure Media Service or something happened in Azure Resource Group etc.
### Integration Runtime
- There are three types of Integration Runtime. They are 
	- Azure
	- Self-Hosted,
	- Azure-SSIS
	
  |  Public Network Support | Private Link Support |
|-|-|-|
Azure | Data Flow ,Data movement, Activity dispatch | Data Flow ,Data movement, Activity dispatch
Self-hosted | Data movement, Activity dispatch | Data movement, Activity dispatch
Azure-SSIS | SSIS package execution | SSIS package execution

- Usage of the above given options such that use SSIS only when the necessary of the SSIS is given else leave it out of choice and the if it has to be hosted by you to keep the data private then the **Self-Hosted** is fine else if we use the **Azure Tools** Then the **Azure** hosting is fine.

### Power Qurey
- A simple tool that is similar to the Microsoft's tool called **Power BI**.
- This power query can also be performed by orchestra such that the pipeline can be created by selecting the source and destination sink.
- Select the trigger that is required for the pipeline and the run it as use wish.

### Flowlet
- Create a new flowlet by clicking the data flow option and then create a source and destination and in the middle give all the required transformation process that is required based on our requirement in the canvas. 
- Then later after specifying the data flow then it can be used as a simple data source for our data flow as all the business logic is stored in that specific flowlet it can be reusable at anytime we want without manually doing it over and over.
- These flowlets helps us to manage us the more complex data flows without any complecity as it can be done by single flowlet.
---
