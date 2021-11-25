### Developer guide 

The connector was created as follows:
- Generated a custom connector off the REST API's swagger/openAPI file. 
  (It has to be Open API 2 since only that is supported) 
  You can generate this connector via in the powerapps portal, select 'Create connector from OpenAPI file'. 
- Gave the actions names and IDs.
- Add the Dynamic Host Url policy to allow for different API endpoints for customers ( https://docs.microsoft.com/en-us/connectors/custom-connectors/policy-templates/dynamichosturl/dynamichosturl ).
- Downloaded the connector with the paconn tool.
- Added custom API endpoint parameter to apiProperties file.
- Altered some return and send types accordingly.
- Added description to apiDefinition file (paconn would crash without it).
- The original generated connector had to be deleted.
- Used `paconn create` to reupload.
- Used `paconn update` afterwards for more changes.

The Paconn CLI tool can be found here (requires az tool):
https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli

You can set up a developer account to develop and test, free of charge, more information here:
https://go.microsoft.com/fwlink/?linkid=847282
