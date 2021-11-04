#Exasol Connector for Power Apps

##Preparation / Requirements
You should first set up the Exasol REST API in case you haven't done so. (see: https://github.com/exasol/exasol-rest-api)


## How to utilize the Exasol Connector for Power Apps.

Currently you'll need to use the paconn tool (installation instructions found here: https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli ) to create or update the connector in your organisation.

### Getting the connector files

Clone this repository, download the zip or download the latest release from github and unzip the files.
You should have a settings file, an icon file and a 

### Using the paconn CLI tool to upload/create the connector within your organisation.

Open up a CLI/Terminal.

First you'll need to authenticate in paconn, type:
paconn login

Next you need to navigate to the folder where you downloaded or unzipped the connector files

Run the following command:
paconn create -s [Path to settings.json]
You'll be prompted to select a Power Apps environment. Follow the steps.
If you get prompted to alter settings.json press 'yes' (it will update the id of the connector).

### Finding the connector 

If you now browse to https://make.powerapps.com/ and click on the 'Dataverse' tab to the left and then 'Custom Collectors' you should be able to see the connector.

### Making a connection using the connector

Under the Dataverse tab, select connections.

Next, click on 'new connection'
In the search bar on the top right, search for 'custom'
You'll find the connector in the search results, select it.

A modal will pop up, you will be asked to configure the connector.
There's 2 values you need to fill in 
API Endpoint, which is where your rest api is hosted or available (this can be an ip address or dns name)
API Key, this is one of the authentication keys you've configured for the rest api. (This is a secure parameter so this API Key will not be retrievable afterwards in the Power Apps UI. )

(You can still edit these 2 values afterwards)

### Optional: Testing the connector through a connection
TODO: Is there a need for this section? Maybe move it to the developer's guide

### Using the connector in a Power App

Finally, we can start using the connector via this connection in power apps. 
Click 'Create' in the left tab.

For this example we'll select 'Create from blank'

### Quick example using insertRow and getRows

### An overview of the available endpoints and how to use them

#### getRows, using flows to parse json for generic objects

### Updating your local version of the connector

First you'll need to authenticate in paconn, type:
paconn login
paconn update -s [Path to settings.json]

## Certification : Towards the future 

Currently we're working on getting our connector certified so it will automatically be available under the connectors in the dataverse tab.