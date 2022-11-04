Exasol is an analytics-focused parallelized relational database management system (RDBMS).
Connect to Exasol databases to create, read, update and delete data.

## Prerequisites

You will need the following to proceed:
* A Microsoft Power Apps or Power Automate plan
* An Exasol database
* Exasol REST API set up, internet facing

## How to get credentials

Currently the connector uses an API Key as the default authentication method.   
The API key(s) can be set in the Exasol REST API which you're also required to set up to use this connector.

## Get started with your connector

You should first set up the Exasol REST API (see: https://github.com/exasol/exasol-rest-api).

The connector itself takes 2 parameters when creating a new connection:

`Host`: Where your REST API is hosted (this can be an IP address or DNS name).

`API Key`: This is one of the authentication keys you've configured to gain access to the REST API.

Note: You can still edit these 2 values afterwards.

Please see the user guide for more detailed instructions and a full tutorial [here](https://github.com/exasol/power-apps-connector/blob/main/doc/user_guide/user_guide.md).

## Known issues and limitations

Using a on-premises data gateway is currently not supported.

## Common errors and remedies

## FAQ
