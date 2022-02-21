## How to install the Exasol Connector for Power Apps.

Currently you'll need to use the paconn tool to  create or update the connector in your organisation.

(installation instructions found here : https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli ) 

The connector talks to the exasol-rest-api which you'll also need to setup if you haven't done so yet.

### Getting the connector files

Clone this repository, download the repository zip or download the latest release from github and unzip the files.
The connector consists of a settings file, an icon file and a apiDefinition.swagger.json and apiProperties.json file which describe the connector.

### Using the paconn CLI tool to upload/create the connector within your organisation.

Open up the command line or a terminal.

###### Authenticate

First you'll need to authenticate in paconn, type:
`paconn login`
Follow the steps to succesfully authenticate.

###### Creating the connector

Next you need to navigate to the folder where you downloaded or unzipped the connector files.

Run the following command:
`paconn create -s [Path to settings.json]`
You'll be prompted to select a Power Apps environment. 

Pick the environment where you want to install the connector.
Follow the steps.
If you get prompted to alter settings.json, press "yes". 

( It will update the id of the connector so you can easily update it afterwards using `paconn update -s [Path to settings.json]`).

###### Inspecting the connector we just created in our environment/organisation.

If you now browse to https://make.powerapps.com/ , pick the right organisation top right and click on the "Dataverse" tab to the left and then "Custom Connectors" you should be able to see the connector.

![image-20211122114520362](user_guide.assets/image-20211122114520362.png)

###### Configuring the connector

You can further configure the connector via the edit icon if you so wish (this is an optional step):

![image-20211122115800918](user_guide.assets/image-20211122115800918.png)

Here you can: 

- Enable HTTPS in case of the HTTP version.
  Before you do so: There's also a HTTPS version of the connector available for download.

![image-20211122114543409](user_guide.assets/image-20211122114543409.png)

Enabling HTTPS is a 2 step process in our connector's case, you'll also need to alter the host URL policy's Url template.

Change "http" into "https". 

![image-20211125134028331](user_guide.assets/image-20211125134028331.png)

### Making a connection using the connector

Under the "Dataverse" tab, select "Connections".

Next, click on "New connection".
In the search bar on the top right, search for "custom".

You'll find the connector in the search results, select it.

![image-20211122114400236](user_guide.assets/image-20211122114400236.png)

A modal will pop up, you will be asked to configure the connector.

![](user_guide.assets/2021-11-22-11-07-29-image-16375779996591.png)

`Host`: Where your REST API is hosted (this can be an IP address or DNS name).

`API Key`: This is one of the authentication keys you've configured to gain access to the REST API. 

This is a secure parameter so this API Key will not be retrievable afterwards in the Power Apps UI.

Note: You can still edit these 2 values afterwards.

### Testing the connector

Since we now have a connector and a connection we can test if everything is configured properly.

![image-20211122115250181](user_guide.assets/image-20211122115250181.png)

To do so, go back to the connector tab, edit the connector, select "Test" at the top, pick the connection you created and run some tests.

I personally always test the connector with the `GetTables` action. 

You'll get a list of tables the database user has access to returned to you in the response if everything 's configured properly.

### Next steps

You're now ready to start [using the connector in a Power App](user_guide.md#using_the_connector_in_a_power_app): 