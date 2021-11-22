# Exasol Connector for Power Apps

## Preparation / Requirements
You should first set up the Exasol REST API in case you haven't done so. (see: https://github.com/exasol/exasol-rest-api)

## How to install the Exasol Connector for Power Apps.

Currently you'll need to use the paconn tool (installation instructions found here: https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli ) to create or update the connector in your organisation.

The connector talks to the exasol-rest-api which you'll also need to setup. See the section above.

### Getting the connector files

Clone this repository, download the repository zip or download the latest release from github and unzip the files.
You should have a settings file, an icon file and a 

### Using the paconn CLI tool to upload/create the connector within your organisation.

Open up a CLI/Terminal.

First you'll need to authenticate in paconn, type:
paconn login.
Follow the steps to succesfully authenticate.

Next you need to navigate to the folder where you downloaded or unzipped the connector files.

Run the following command:
paconn create -s [Path to settings.json]
You'll be prompted to select a Power Apps environment. Pick the environment where you want to install the connector.
Follow the steps.
If you get prompted to alter settings.json press 'yes' (it will update the id of the connector so you can easily update it afterwards).

### Finding the connector

If you now browse to https://make.powerapps.com/ and click on the 'Dataverse' tab to the left and then 'Custom Collectors' you should be able to see the connector.

![image-20211122114520362](user_guide.assets/image-20211122114520362.png)



#### Configuring the connector

You can further configure the connector via the edit icon:

![image-20211122115800918](user_guide.assets/image-20211122115800918.png)



Here you can enable HTTPS (it uses HTTP by default) or if you wish to use a gateway.

![image-20211122114543409](user_guide.assets/image-20211122114543409.png)

### Making a connection using the connector

Under the Dataverse tab, select connections.

Next, click on 'new connection'
In the search bar on the top right, search for 'custom'
You'll find the connector in the search results, select it.

![image-20211122114400236](user_guide.assets/image-20211122114400236.png)

A modal will pop up, you will be asked to configure the connector.

![](user_guide.assets/2021-11-22-11-07-29-image-16375779996591.png)
Host: which is where your rest api is hosted or available (this can be an ip address or dns name)
API Key: This is one of the authentication keys you've configured for the rest api. (This is a secure parameter so this API Key will not be retrievable afterwards in the Power Apps UI. )

(You can still edit these 2 values afterwards.)

### Testing the connector

Since you now have a connector and a connection we can test if everything is configured properly.

![image-20211122115250181](user_guide.assets/image-20211122115250181.png)

To do so, go back to the connector tab, edit the connector, select "Test" at the top, pick the connection you created and run some tests.

I personally always test with GetTables. 

You'll get a list of tables you have access to returned to you in the response if everything 's configured properly.

# Using the connector in a Power App

## A short overview of the available actions

As you can see from the previous screenshot you'll have 7 connector actions available to you. 

A quick overview:

##### GetTables

Returns a list of the available tables to the user.

##### GetRows

Returns the rows from a table based on filter conditions.

##### InsertRow

Insert a row into a table.

##### UpdateRows

Update row(s) within a table.

##### DeleteRows

Delete row(s) within a table.

##### ExecuteQuery

Run a custom query to fetch data, for more advanced scenarios.

##### ExecuteNonQuery

Run a custom command, for more advanced scenarios.



Finally, we can start using the connector via this connection in power apps. 
Click 'Create' in the left tab.

For this example we'll select 'Create from blank'

### Quick example using insertRow and getRows

#### getRows, using flows to parse json for generic objects

